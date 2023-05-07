---
layout: post
title:  "Job schedule expiration"
date:   2023-05-07 14:45:00 +0200
categories: service news
---
Now you can specify an expiration date for cron jobs, after which they will not be executed anymore. You can find the new option in the cron job editor in the "Execution schedule" box.

Of course this feature can also be used from our [REST API](https://docs.cron-job.org/rest-api.html){:target="_blank"} by setting the `expiresAt` attribute of the `JobSchedule` object.

If you have any feedback or suggestions for us, please let us know at [info@cron-job.org](mailto:info@cron-job.org).
