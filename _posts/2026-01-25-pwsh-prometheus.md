---
title: "Prometheus metrics from PowerShell"
date: 2026-01-25
layout: post
---

PowerShell is one of my favorite languages. The extensibility and features it provides for plugging into systems makes it the optimal tool for building digital glue for sysadmins.

I also really enjoy prometheus' flipped DB model of the DB being responsible for grabbing the data from the source rather than something external being responsible for inserting the data. This can lead to some interesting ideas... like generating prometheus metrics on the fly from PowerShell scripts.

This weekend project, [New-PromMetric](https://github.com/LGDan/New-PromMetric) does exactly that. If you have a PowerShell command that yields a stat from a system, why not surface it as a prometheus metic and track it?

Designed for use with the [pode](https://github.com/Badgerati/Pode) framework, you can build a prometheus exporter in PowerShell to make use of what ever modules and cmdlets are available. Neat!