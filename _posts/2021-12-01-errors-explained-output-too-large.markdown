---
layout: post
title:  "Errors explained: Output too large"
date:   2021-12-01 15:00:00 +0200
categories: service
---
In case your cron job at cron-job.org fails with an error like "Failed (output too large)", the URL you provided is producing too much output data. In this article, we’re explaining the background of this error and what you can do in order to resolve it.

# Background

Sometimes, cron scripts output a lot of verbose information when executed. In most cases, this is not required at all, since that output data will be discarded anyway and nobody will look at it.

However, in order to correctly execute the job, cron-job.org has to read and consume all the output data — otherwise, at some point, the cron script would get stuck with a full output buffer.

In order to protect the cron-job.org service from abuse and denial of service attacks (e.g. by providing a big download, say an ISO image, as the cron job URL), we’re limiting the maximum amount of data the URL can return. When the maximum amount is exceeded, cron-job.org will close the connection to the peer server and mark the job as "Failed".

# How to resolve

In case you’re the cron script author or you can edit it, we strongly recommend to change your script in a way that it outputs no data at all, or only outputs a short status message like "OK" or "Error". If you need diagnostic information like logs, we recommend to dump them to a log file instead of returning them as output of your script.

In case you’re using a cron script of a software product you can’t change, check if there’s a way to set the output to a less verbose level. If in doubt, contact the author of the software product you’re using and ask them how to reduce the procuded output. You might also want to refer them to this article for explanation.

Last but not least, with a cron-job.org Sustaining Membership, you can get a higher limit of allowed output data. Check "Settings" in the [cron-job.org Console](https://console.cron-job.org){:target="_blank"} for more details.
