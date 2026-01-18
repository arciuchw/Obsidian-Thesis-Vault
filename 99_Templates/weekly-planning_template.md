---
created: <% tp.file.creation_date() %>
week-start: "<% moment().startOf('isoWeek').format('YYYY-MM-DD') %>"
week-end: "<% moment().startOf('isoWeek').add(6, 'days').format('YYYY-MM-DD') %>"
cssclasses: cornell-table
---
---
# 📅 Weekly Planning
**Week of:** <% moment().startOf('isoWeek').format("MMMM Do") %> - <% moment().startOf('isoWeek').add(6, "days").format("MMMM Do, YYYY") %>

---

## 🎯 This Week's Goals

### Reading Goals
- [ ] Complete pass on: 
- [ ] Start reading: 
- [ ] Finish book chapter: 

### Writing Goals
- [ ] Merge synthesis: 
- [ ] Draft section: 
- [ ] Review and refine: 

---

## 🗓️ Daily Breakdown

| Day | Reading & Writing Tasks | Notes |
| :--- | :--- | :--- |
| **Monday** | | |
| **Tuesday** | | |
| **Wednesday** | | |
| **Thursday** | | |
| **Friday** | | |
| **Weekend** | | |

---

## 📊 Progress Tracking (Auto-Generated)

### 📚 Reading Completed This Week
> [!info] Shows notes updated between Monday and Sunday

```dataview
TABLE reading-status as Status, last-visited as "Last Visited"
FROM "10_Concepts" OR "20_Merges"
WHERE last-visited >= date("<% moment().startOf('isoWeek').format('YYYY-MM-DD') %>") AND last-visited <= date("<% moment().startOf('isoWeek').add(6, 'days').format('YYYY-MM-DD') %>")
SORT last-visited DESC
```

### ✍️ Drafts Advanced This Week
```dataview
TABLE status as Status, last-visited as "Last Visited"
FROM "30_Drafts"
WHERE last-visited >= date("<% moment().startOf('isoWeek').format('YYYY-MM-DD') %>") AND last-visited <= date("<% moment().startOf('isoWeek').add(6, 'days').format('YYYY-MM-DD') %>")
SORT last-visited DESC
```
