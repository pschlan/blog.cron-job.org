---
layout: post
title:  "Errors explained: Timeout"
date:   2021-12-01 15:00:00 +0200
categories: service
---
If your cron job fails with a timeout error, the script/URL you’re calling is taking too much time to respond. This article explains the background of this error and what you can do in order to resolve it.

# Background

When executing a cron-job, the cron-job.org service connects to the server serving the URL you’ve specified and submits a HTTP request according to your job configuration. Usually this will trigger execution of a script on the server side. For example, it will invoke a PHP or Python/Ruby script.

Most servers are configured to execute the script while the request is active. That means that the script will be aborted whenever the client (e.g. a browser or cron-job.org’s execution engine) aborts the requests / closes the connection.

Hence it’s important for cron-job.org to keep the connection open until the server closes it, signalling that execution has completed.

Since such an open connection occupies resources on our side, we have to limit the maximum execution time. Otherwise, malicious users could overload our service with many connections kept open for a long time, and we’d run out of resources — leading to failing executions of other users.

Currently, the default execution time limit is 30 seconds. This guarantees the service can finish a job within the minute it is executed.

# How to resolve

In order to resolve a timeout error, your script needs to be changed in a way that it doesn’t execute for long time. If your script has lots of work to execute, you could monitor its execution time (in PHP e.g. by calling microtime()) and exit the script when it’s close to the execution time limit. Next time the job is executed, the script could continue where it stopped previously.

In case you can’t change the script accordingly, you can still consider becoming a Sustaining Member at cron-job.org, which will give you a higher execution time limit. Check "Settings" in the [cron-job.org Console](https://console.cron-job.org){:target="_blank"} for more details.
