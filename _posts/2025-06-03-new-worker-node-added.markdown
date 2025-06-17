---
layout: post
title:  "New worker node added"
date:   2025-06-03 21:00:00 +0200
categories: service news
---
Tto keep up with the growth of our service, we’ve added yet another additional worker to our fleet of job executors. This will stop load increase on our existing nodes and ensure our service scales seamlessly as you add new jobs.

In case you’re using an IP-based allowlist or a firewall to protect your cron jobs, please ensure you add the new IP address `91.99.23.109`.

Usually we don’t move jobs between nodes once they’re created, so this should affect new jobs only. Your existing jobs will continue to be executed from the usual IP addresses.

We’ve also extended our [FAQ](https://cron-job.org/faq/) and our [JSON list of node IPs](https://api.cron-job.org/executor-nodes.json) to include the new worker’s IP address.
