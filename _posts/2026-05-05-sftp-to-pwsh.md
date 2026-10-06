---
title: "SFTP to... PowerShell?"
date: 2026-05-05
layout: post
---

Don't ya just hate it when some massive blackbox SaaS application you pay **copius** amounts of money for refuses to offer any kind of integration protocol apart from connecting to an SFTP server? What's REST? When did that happen? What are webhooks? What's pubsub? How long has amqp been around? Ugh. Time to build another cursed protocol adapter.

[pwsh-rclone-serve](https://github.com/LGDan/pwsh-rclone-serve) is my project of this week, a docker container that presents an SFTP server, but the files on it are all virtual. They don't exist, and instead point to PowerShell scripts that generate the "data in the file" on-the-fly as they're accessed. There are two elements of special sauce in here.

1.  The universal network storage swiss army knife, [rclone](https://rclone.org) which handles the running of the first protocol adapter - SFTP to HTTP
2. A good ol' CGI server on Apache, providing HTTP-to-script-to-stdout-to-HTTP

Rclone expects an apache directory listing (Index of /) to serve up via SFTP, and Apache will run what ever files you tell it to treat as scripts via CGI.

When that script is a PowerShell script, you have a lot of flexibility. Any powershell modules can now become exposed data interfaces with constrains that you set, and format/protocol transforms like `ConvertTo-Csv` and `ConvertTo-Json`. *Options may include and are not limited to:*

- AD Users
- Mailboxes
- SQL Queries
- Other web requests!
- Dirty horrible excel sheets?
- SNMP Requests?
- WMI Rubbish
- Inventory system data
- ITSM tickets
- [Grist](https://getgrist.com) data!
