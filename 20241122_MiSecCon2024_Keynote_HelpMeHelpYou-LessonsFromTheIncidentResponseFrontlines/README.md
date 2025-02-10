# Help Me Help You: Lessons from the Incident Response Frontlines

[![Help Me Help You: Lessons from the Incident Response Frontlines](https://img.youtube.com/vi/i7VvM5zEdDQ/0.jpg)](https://www.youtube.com/watch?v=i7VvM5zEdDQ)

* Date: 2024-11-22
* Conference: [MiSecCon 2024](https://miseccon.misec.us/)
* Abstract: Incident response is a collaborative effort. Learn how proactive preparation for the inevitable can help provide the best outcomes for the IR team and, more importantly, YOUR team. Also, learn what practices other proactive sysadmins have implemented in their networks that have made IR professionals sigh in relief! The key goal of this talk is to gain a mutual understanding of the low-risk, high-reward quick wins that will help answer questions more effectively when the pressure is on.

## Errata

At [42:20](https://youtu.be/i7VvM5zEdDQ?t=2540), I meant to go back to the `Summary of Host Timeline` slide but, in the moment, I forgot to go back, which is very unfortunate!


Below is the timeline of events observed (at a high level) on this host:

```
16:08:12 | HOST01 | DOMAIN\admin | RDP Connect
16:11:45 | HOST01 | DOMAIN\admin | File Download - AnyDesk
16:12:02 | HOST01 | DOMAIN\admin | Program Execution - AnyDesk
16:12:33 | HOST01 | Files Created - evil.exe & evil.ps1
16:13:11 | HOST01 | Files Executed - evil.exe & evil.ps1
16:39:56 | HOST01 | DOMAIN\admin | Outbound RDP to multiple hosts
18:03:14 | HOST01 | DOMAIN\admin | RDP Disconnect 
18:04:27 | HOST01 | $J – DataTruncate | AnyDesk – ad.trace
18:04:45 | HOST01 | $J – DataTruncate | AnyDesk – ad.trace
```

The TA still had an active AnyDesk connection where they deleted 90%+ of the `ad.trace` file in question, bringing the overall size of `ad.trace` from ~990kb to ~90kb.
