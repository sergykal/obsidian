---
created: ""
updated: ""
tags:
  - weekly-note
---
---
# Weekly Agenda

- [ ] 

---
# Schedule

- [ ] 

---
# Notes

- 
---

# Weekly Review

```dataview
TABLE WITHOUT ID
  file.link   AS "Note",
  file.cday   AS "Date Created",
  file.tags   AS "Tags"
WHERE
  file.cday >= date(this.updated)
  AND file.cday < date(this.updated) + dur(7 days)
SORT file.cday asc

```
