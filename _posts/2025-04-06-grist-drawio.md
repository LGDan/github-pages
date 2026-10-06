---
title: "Do diagrams dream of electric spreadsheets"
date: 2025-04-06
layout: post
---

I like ~~forcing people to build spreadsheets that make sense~~ [grist](https://getgrist.com) and I like [diagrams](https://draw.io). Especially diagrams with proper intentionality. Good diagrams are an artform. So are good spreadsheets.

## Spreadsheets on .wheels

Grist stood out for me as a bit of a wildcard product - it's got a strong motivated community behind it, the free selfhosted version isn't feature-nerfed, and my god can you do some complex stuff with it. Each column is strongly typed, it's backed by an SQL database, and it supports python functions in place of excel functions. Not just basic python either - you can import full libraries! This means XML parsing, JSON parsing, list comp, playing with sets, even HTTP requests!

On my neverending quest to find a good EA tool, I truly felt grist hit a sweet spot between a CMDB, a spreadsheet, and a BI tool. A solid trifecta for managaing EA assets. The one problem is that it's a tabular database. No diagrams, no [good EA] visuals, just rows and columns. To someone you share it with, the first question is "what is this" and the second comment is "you could have used excel". Shudder.

What grist needed was a way of both ingesting 'drawn' information, and outputting visual information. If only I knew of an [awesome diagramming tool](https://draw.io) that's natively browser based, and stores data in an [easily parsable format](https://www.drawio.com/docs/manual/editor/save-file-formats/), and supports being [natively embedded](https://www.drawio.com/docs/tutorials/embedding-walkthrough/) in other web apps...

Behold my creation, the [draw.io custom widget for grist](https://github.com/LGDan/grist-widget-drawio). Edit diagrams all within grist, and save them back as XML to a cell. Parse the XML with python and generate references to other objects in the tables.

---

Update 2025-07: I got a [shout-out](https://www.getgrist.com/webinars/community-custom-widget-showcase/) from Grist themselves. Neat!