---
layout: post
title:  "New node added to worker fleet"
date:   2023-05-07 21:00:00 +0200
categories: service news
---
Today, to keep up with the growth of our service, we’ve added yet another additional worker to our fleet of job executors. This will stop load increase on our existing nodes and ensure our service scales seamlessly as you add new jobs.

In case you’re using an IP-based allowlist or a firewall to protect your cron jobs, please ensure you add the new IP address `128.140.8.200`.

Usually we don’t move jobs between nodes once they’re created, so this should affect new jobs only. Your existing jobs will continue to be executed from the usual IP addresses.

We’ve also extended our FAQ to include the new worker’s IP address.
