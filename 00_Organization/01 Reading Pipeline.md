# 📊 Reading Pipeline

**Purpose:** Track all reading tasks across your research. Filter by status, relevance, and topic.

---

## Current Reading Queue

### High Priority (Thesis Core)

```dataview
LIST WITHOUT ID
FROM "10_Concepts" OR "20_Merges"
WHERE thesis-relevance = "🔥 core" OR thesis-relevance = "⭐️⭐️⭐️ high"
AND reading-status != "✅ complete"
SORT reading-status ASC
```

### Medium Priority (Supporting Evidence)

```dataview
LIST WITHOUT ID
FROM "10_Concepts" OR "20_Merges"
WHERE thesis-relevance = "⭐️⭐️ medium"
AND reading-status != "✅ complete"
SORT last-visited DESC
```

---

## Reading Status Overview

### Unread Sources

```dataview
TABLE reading-status, thesis-relevance, type
FROM "10_Concepts" OR "20_Merges"
WHERE reading-status = "❔ unread"
SORT thesis-relevance DESC
```

### Currently Reading (Pass 1-2)

```dataview
TABLE reading-status, last-visited, next-action
FROM "10_Concepts" OR "20_Merges"
WHERE contains(reading-status, "1️⃣ pass_1") OR contains(reading-status, "2️⃣ pass_2")
SORT last-visited DESC
```


### Ready for Deep Dive (Third Pass)

```dataview
TABLE reading-status, thesis-relevance, type
FROM "10_Concepts" OR "20_Merges"
WHERE reading-status = "3️⃣ pass_3"
SORT thesis-relevance DESC
```

### Completed

```dataview
LIST WITHOUT ID
FROM "10_Concepts" OR "20_Merges"
WHERE reading-status = "✅ complete"
SORT last-visited DESC
LIMIT 20
```

---

## By Topic

### Topic Name

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
WHERE topic = "[[Topic]]"
AND reading-status != "✅ complete"
SORT thesis-relevance DESC
```

## Next Actions

### Papers Needing Second Pass

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
WHERE reading-status = "1️⃣ pass_1"
AND next-action = "2️⃣ pass_2"
SORT last-visited DESC
```

### Books Requiring Chapter Review

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
WHERE contains(type, "☘️ book-learning") or contains(type, "🍀 book-concept")
AND reading-status != "✅ complete"
SORT last-visited DESC
```


---

## Statistics

### Reading Progress

```dataview
LIST WITHOUT ID
FROM "10_Concepts" OR "20_Merges"
GROUP BY reading-status
```

### Thesis Relevance Distribution

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
GROUP BY thesis-relevance
```