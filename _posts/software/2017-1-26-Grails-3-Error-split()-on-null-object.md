---
layout: post
title: "Grails 3 Error: split() on null object"
author: icha
description: "Error occurred running Grails CLI: Cannot invoke method split() on null object"
modified: 2017-1-26
category: software
thumbnail: grails-development-company.png
tags: [grails 3, errors]
---

## Story
----

I experienced this error when trying to deploy an application on a VPS. It was in Ubuntu 16.04 and the Java was openjdk 8.


```bash
$ grails prod run-app
| Error Error occurred running Grails CLI: Cannot invoke method split() on null object (Use --stacktrace to see the full trace)
```

When I use `--stacktrace`:

```bash
$ grails prod run-app --stacktrace
| Error Error occurred running Grails CLI: Cannot invoke method split() on null object (NOTE: Stack trace has been filtered. | Use --verbose to see entire trace.)
java.lang.NullPointerException: Cannot invoke method split() on null object
        at script14854150227601407668926$_run_closure1$_closure2$_closure4.doCall(script14854150227601407668926.groovy:9)
        at script14854150227601407668926$_run_closure1$_closure2$_closure4.doCall(script14854150227601407668926.groovy)
        at script14854150227601407668926$_run_closure1$_closure2.doCall(script14854150227601407668926.groovy:3)
        at script14854150227601407668926$_run_closure1$_closure2.doCall(script14854150227601407668926.groovy)
        at script14854150227601407668926$_run_closure1.doCall(script14854150227601407668926.groovy:2)
        at script14854150227601407668926$_run_closure1.doCall(script14854150227601407668926.groovy)
        at script14854150227601407668926.run(script14854150227601407668926.groovy:1)
        at org.grails.config.CodeGenConfig.loadGroovy(CodeGenConfig.groovy:148)
        at org.grails.cli.GrailsCli.loadApplicationConfig(GrailsCli.groovy:592)
        at org.grails.cli.GrailsCli.initializeApplication(GrailsCli.groovy:291)
        at org.grails.cli.GrailsCli.execute(GrailsCli.groovy:269)
        at org.grails.cli.GrailsCli.main(GrailsCli.groovy:159)
| Error Error occurred running Grails CLI: Cannot invoke method split() on null object
```

Somehow it happened only when using production environment. When using development or test environment, the application ran as usual.

I had googled and didn’t find any links matched my error, but I came with several solutions. I tried these solution and didn’t solve the problem. Here is some solutions that I found:

1. Add `$JAVA_HOME/bin` to path variable
2. Set `GRAILS_OPTS` environment variable, with value `"-XX:-UseSplitVerifier -Xverify:none"`
3. Change Java to openjdk 7


Finally I gave up and tried another way to run the application. I tried to build the application as war and ran as java application.
This is what I did:

```bash
$ grails war
$ java -Dgrails.env=prod -jar build/libs/myApp.war -server -Xmx768M -XX:MaxPermSize=256m
```

Voila, another error occurred! Actually it was the same error as earlier. But it came with useful hints of the error.

```bash
Caused by: org.grails.core.exceptions.GrailsConfigurationException: Error loading application.groovy due to [java.lang.NullPointerException]: Cannot invoke method split() on null object
```

So from there, I went to my `application.groovy`, and check my configuration for production environment. This was written before:

```groovy
environments {
  production {
     dataSource {
        dbCreate = "update"
        driverClassName = "org.postgresql.Driver"
        dialect = org.hibernate.dialect.PostgreSQL94Dialect
        uri = new URI(System.env.DATABASE_URL?:"postgres://localhost:5432/test")
        url = "jdbc:postgresql://" + uri.host + ":" + uri.port + uri.path + "?sslmode=require"
        username = uri.userInfo.split(":")[0]
        password = uri.userInfo.split(":")[1]
     }
  }
}
```

Stupid me! This error was because of the uri was null, which was because I didn’t set my `DATABASE_URL` environment variable. Yeah, I had ran the application in Heroku before, so that was the configuration that I used. So the solution for my problem was just set `DATABASE_URL` environment variable, then I could run the application using grails run-app or using java.

## Finally
----

If you also experience this problem, then just check what may cause the error. It may be just a stupid mistake, in my experience it was the `DATABASE_URL` environment variable in `application.groovy`. Good luck!