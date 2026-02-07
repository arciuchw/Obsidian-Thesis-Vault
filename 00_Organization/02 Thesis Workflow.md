# ✍️ Thesis Writing Workflow

**Purpose:** Track thesis sections and connect them to supporting merges and drafts.

---

## Thesis Outline & Status

| Section             | Status        | Draft? | Sources | Notes |
| ------------------- | ------------- | ------ | ------- | ----- |
| **1. Introduction** | ⬜ Not Started | No     |         |       |
| **2. Background**   | ⬜ Not Started | No     |         |       |
| **3. Related Work** | ⬜ Not Started | No     |         |       |
| **4. Methodology**  | ⬜ Not Started | No     |         |       |
| **5. Results**      | ⬜ Not Started | No     |         |       |
| **6. Discussion**   | ⬜ Not Started | No     |         |       |
| **7. Conclusion**   | ⬜ Not Started | No     |         |       |

---

## Drafts in Progress

### All Current Drafts

```dataview
TABLE status, thesis-section
FROM "30_Drafts"
WHERE status != "✅ complete"
SORT status DESC
```

---

## Merges Supporting Each Section

### For Introduction

```dataview
LIST WITHOUT ID
FROM "20_Merges"
WHERE contains(thesis-section, "Introduction")
SORT status ASC
```

### For Background / Literature Review

```dataview
LIST WITHOUT ID
FROM "20_Merges"
WHERE contains(thesis-section, "Background") OR contains(thesis-section, "Literature")
SORT status ASC
```

### For Methodology

```dataview
LIST WITHOUT ID
FROM "20_Merges"
WHERE contains(thesis-section, "Methodology")
SORT status ASC
```

### For Results / Discussion

```dataview
LIST WITHOUT ID
FROM "20_Merges"
WHERE contains(thesis-section, "Results") OR contains(thesis-section, "Discussion")
SORT status ASC
```

---

## Concept-to-Merge-to-Draft Pipeline

### Unprocessed High-Relevance Concepts

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
WHERE thesis-relevance = "🔥 core" OR thesis-relevance = "⭐️⭐️⭐️ high"
AND (contains(reading-status, "2️⃣ pass_2") OR  contains(reading-status, "3️⃣ pass_3") OR contains(reading-status, "✅ complete"))
SORT last-visited DESC
```

**Action:** These concepts should feed into merges.

### Merges Not Yet Drafted

```dataview
LIST WITHOUT ID
FROM "20_Merges"
WHERE contains(status, "❌ not started") OR contains(status, "🔨 in progress")
SORT status ASC
```

**Action:** Prioritize drafting these merges.

---

## Citation Tracking

### Sources Ready to Cite (Highly Relevant + Complete)

```dataview
TABLE authors, year, thesis-relevance, reading-status
FROM "10_Concepts"
WHERE cited = false
AND reading-status = "✅ complete"
AND contains(thesis-relevance, "🔥 core") OR contains(thesis-relevance, "⭐️⭐️⭐️ high")
SORT thesis-relevance DESC
```

### Recently Cited Sources

```dataview
TABLE cited, last-visited, thesis-relevance
FROM "10_Concepts"
WHERE cited = true
SORT last-visited DESC
LIMIT 15
```

---

## Writing Statistics

### By Thesis Relevance

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
GROUP BY thesis-relevance
```

### By Type (Papers vs Books)

```dataview
LIST WITHOUT ID
FROM "10_Concepts"
GROUP BY type
```

### Completion Progress

```dataview
LIST WITHOUT ID
FROM "10_Concepts" OR "20_Merges"
GROUP BY reading-status
```