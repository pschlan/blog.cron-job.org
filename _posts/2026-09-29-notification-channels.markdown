---
layout: post
title:  "Notification channels"
date:   2026-09-29 10:00:00 +0200
categories: service news
---
We've enhanced our notification feature: you can now add multiple notification channels, including email and webhook destinations.

You can configure your notification channels in our [Console](https://console.cron-job.org){:target="_blank"} under "Settings".

![Screenshot of the new notification channel editor](/assets/2026/09/notification-channels.png)

We also have presets for popular notification and messenger services.

![Screenshot of the channel add dialog](/assets/2026/09/add-channel.png)

When editing a job, you can choose which notification channels to use.

![Screenshot of channel selection in the job editor](/assets/2026/09/job-notification-channels.png)

For webhook and messenger deliveries, we attempt delivery up to 3 times, with a timeout of 20 seconds per attempt.

As usual, if you have any feedback or suggestions for us, please let us know at [info@cron-job.org](mailto:info@cron-job.org).
