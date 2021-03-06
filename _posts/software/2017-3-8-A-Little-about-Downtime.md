---
layout: post
title: "A Little about Downtime"
author: alifa
description: "downtime, failures, and availability"
modified: 2017-03-08
category: software
imagefeature: downtime.jpg
tags: [downtime, failure, availability]
fb-url: https://www.facebook.com/catalinageekgirl/posts/1550627401631445
---

Last week is not a usual one for the company I working for. On Wednesdey Afternoon, someone spoke loudly “www.tokopedia.com down ya??”. Yes, it was a very long down time caused by failure at Biznet Data Center. That incident reminds me to one lesson on graduate study. So I write this short post for you geeks!

This topic is strongly related with two terms: availability and reliability. Those two terms that sometimes considered as same meaning. So what’s the difference? Is availbility same as reliability? I have outlined the definition from references. 
* <b>Availability</b> is the percentage in time when a system on operational state.
* <b>Reliability</b> represents probability a system give correct answers in some time interval. 

How geeks? I think availability is much more easier to understand. Just keep it geeks, or ignore first if it hard to be understood. Now we move to the topic itself.

## Downtime
-----
Downtime is time interval when a system is not available. Downtime is also called outage duration. On the real life, there are several causes of downtime, which mostly comes with failures:
* <b>Hardware Failure</b>
This failure comes from physical components of a server—the storage drives, the processors (CPUs), memory (RAM), and motherboards. These failures are the top causes of server crash. They can also come with natural disaster or power failure.
* <b>Software Failure</b>
Software failures come with the root causes in operating system, server software, or the system itself that can be any logic errors, overload, etc.
* <b>Human Error</b>
Human error is also a possible cause of system down. It can be fault on configuration, file corrupts, file deletion, and other inadvertence actions.
* <b>Maintenance</b>
How about maintenance? Yes, sheduled maintenance is included to downtime, and included in availability calculation. Why? Though it aims to upgrade the system, from users' view maitenance still be annoying one and of course from business view, there will be such impacts to the GMV.

From those causes, we can conclude that downtime has big probability comes from the third party, not from our system itself. So that the use of back-up is very important here. Backup is not only about the data, backup server resources are also important. The backup (data, application server, etc) can be used as temporary resources, until the main resources up again. Though the transfer is not easy, it's difficult, especially for a large scale system with large amount of users.

## Availability
-----
From the definition of downtime above, in formal notation, availability can be calculated using this formula:

<b> Availability = MTBF /(MTBF + MTTR) </b>

Those terms are commonly used if we talk about availibility inside classes. <b>MTBF</b> stands for Mean Time Between Failures, so you can simply assume it as uptime. Then, <b>MTTR</b> is Mean Time to Repair, the times used to make a system up again, it is can be assumed as downtime.  Downtime often measured on a year (365 days) interval and the availability is often presented in nines notation. For example 3-nines corresponds to 99.9% availability and 5-nines corresponds to 99.999% availability like on the table below. As you can see on the table, the difference downtime each one nine increment is very big.

<div class="row center">
  <div class="large-12 columns">
    <table>
      <thead>
        <tr>
          <th>Availability</th>
          <th>Downtime</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>90% (1 nine)</td>
          <td>36,5 days/year</td>
        </tr>
        <tr>
          <td>99% (2 nines)</td>
          <td>3,65 days/year</td>
        </tr>
        <tr>
          <td>99,9% (3 nines)</td>
          <td>8,76 hours/year</td>
        </tr>
        <tr>
          <td>99,99% (4 nines)</td>
          <td>52 minutes/year</td>
        </tr>
        <tr>
          <td>99,999% (5 nines)</td>
          <td>5 minutes/year</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

## Yeah!
-----

Oke, there are such things I can share about downtime and friends (availibity, failures, and reliability). Sorry for random topic and for the mistakes, because I am not a pro. Thank you!

### References

* https://en.wikipedia.org/wiki/Reliability,_availability_and_serviceability
* http://www.eventhelix.com/RealtimeMantra/FaultHandling/reliability_availability_basics.htm#.WLqzdxKGOYU
* http://reliabilityweb.com/tips/article/understanding_the_difference_between_reliability_and_availability
* https://en.wikipedia.org/wiki/Downtime
* http://www.monitance.com/en/tips-for-using-monitance/server-downtimes-impact-causes-and-avoidance/
* http://www.sweetapollo.co.uk/wp-content/uploads/2013/11/ServerDowntime-800x400.jpg


