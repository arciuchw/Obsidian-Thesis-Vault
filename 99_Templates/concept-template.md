---
title: "{{title}}"
authors: "{{authors}}"
year:
  "{ year }":
zotero_key: "{{citekey}}"
created: <% tp.file.creation_date() %>
type: 🌱 concept
reading-status: ❔ unread
topic: "[[Unsorted]]"
thesis-relevance: ❔undefined
next-action: 1️⃣ pass_1
cited: false
last-visited: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm") %>
cssclasses:
  - cornell-table
---

# {{title}}

## Abstract

{{abstract}}

## Annotations & Notes from Zotero

| Cues (Comments/Tags) | Notes (Highlights) |
| :--- | :--- |
{% for annotation in annotations -%}
{%- set colorName = "Highlight" -%}
{%- if annotation.color == "#ffd400" %}{% set colorName = "Yellow" %}
{%- elif annotation.color == "#ff6666" %}{% set colorName = "Red" %}
{%- elif annotation.color == "#5fb236" %}{% set colorName = "Green" %}
{%- elif annotation.color == "#2ea8e5" %}{% set colorName = "Blue" %}
{%- elif annotation.color == "#a28ae5" %}{% set colorName = "Purple" %}
{%- endif -%}
| **{{ annotation.comment if annotation.comment else colorName }}** | <font color="{{annotation.color}}">●</font> {{ annotation.annotatedText | replace("\n", " ") }} [p. {{annotation.pageLabel}}](zotero://select/library/items/{{item.itemKey}}?page={{annotation.pageLabel}}) |
{% endfor %}

---
## Quick Review / First Pass
> [!First pass helper]
> - What are the key concepts?
> - What do I not understand?
> - New terminology
> - Key findings
> - Thesis/Paper relevant fragments

| **Cues & Questions**               | **Class Notes**                                                           |
| :--------------------------------- | :------------------------------------------------------------------------ |
| What is the category of the paper? | (review, methodology paper, empirical study, theoretical framework, etc.) |
|                                    |                                                                           |
| Relevance                          | High/Medium/Low                                                           |

> [!summary]
> Write your summary here

### Decision
- [ ] Continue to second pass
- [ ] Skip (add to "checked but not relevant" archive)

---

## Detailed Review / Second-Third Pass
### Clarification
*What did I not understand?*


### Main Concepts & Terminology
*More detailed view of the concepts  and terminology*


### Key Findings & Arguments
**Important Results/Claims:**

### Figures, Tables & Illustrations
*Analysis of graphs and tables. Insert any relevant graphs for later reference*
**Visual Elements:**
- 

### References & Related Work

**Cited sources I should review:**
- 

### Critical Analysis

**Assumptions to validate:**

**Potential limitations or gaps:**

**How would I approach this differently:**

---

## Related Notes

- [[]]
- [[]]

## Status Log

| Date | Status | Action  |
| ---- | ------ | ------- |
|      |        | Created |
|      |        |         |
