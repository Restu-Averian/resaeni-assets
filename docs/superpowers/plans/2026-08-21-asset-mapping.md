# Asset Mapping Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create `index.html` at the repository root that dynamically queries GitHub Trees API and renders structured JSON mapping of all files in `public/` within a `<pre>` element.

**Architecture:** A lightweight standalone HTML document with embedded Vanilla JS that calls the GitHub API (`https://api.github.com/repos/Restu-Averian/resaeni-assets/git/trees/main?recursive=1`), filters for `public/` files while excluding `.DS_Store` and hidden files, transforms paths into both a flat list and a nested tree hierarchy, and displays pretty-printed JSON in a styled `<pre>` container.

**Tech Stack:** HTML5, Vanilla JavaScript (ES6+ async/await, Fetch API), Vanilla CSS (modern dark aesthetic, responsive, monospace).

## Global Constraints
- Target file: `/Users/mac/Projects/Coding/reseni-assets/index.html`
- Source repository: `Restu-Averian/resaeni-assets`
- Branch: `main`
- Data rendering: inside `<pre>` tag with JSON formatted output.
- Zero manual updates needed when new files are pushed to `public/`.

---

### Task 1: Create `index.html` with Dynamic Tree Fetching and JSON Mapping in `<pre>`

**Files:**
- Create: `index.html`
- Test: `test/verify-mapping.js` or Node.js verification script

**Interfaces:**
- Produces: `index.html` web application.

- [ ] **Step 1: Write Node.js verification test script**
Write a lightweight test script to verify GitHub API tree transformation logic and ensure `.DS_Store` exclusion and nested tree generation match expectations.

- [ ] **Step 2: Run verification script**
Run: `node test/verify-mapping.js`
Expected: Output showing correctly parsed structure.

- [ ] **Step 3: Create `index.html`**
Write clean, robust HTML5 + CSS + JS in `index.html`.

- [ ] **Step 4: Verify rendering and browser testing**
Validate `index.html` works and properly outputs JSON in `<pre>`.

- [ ] **Step 5: Clean up test scripts and commit**
Commit the changes.
