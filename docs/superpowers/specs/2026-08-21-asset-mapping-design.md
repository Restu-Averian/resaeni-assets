# Asset Mapping Page Design Document

## Goal
Build a single static `index.html` file at the root of `reseni-assets` repository that automatically lists and maps all public assets in structured JSON inside a `<pre>` tag dynamically using GitHub Trees API.

## Requirements
1. **Source of Truth**: Dynamic fetch against GitHub Trees API for repository `Restu-Averian/resaeni-assets` on the `main` branch (`https://api.github.com/repos/Restu-Averian/resaeni-assets/git/trees/main?recursive=1`).
2. **Filtering**:
   - Only include files whose path begins with `public/` and is a blob (`type: "blob"`).
   - Exclude hidden system files such as `.DS_Store`, `.gitignore`, etc.
3. **Data Structure**:
   - `meta`: repository name, branch, fetched timestamp, total items.
   - `files`: list of objects containing relative path, clean path (without `public/`), and full raw GitHub/CDN URLs.
   - `tree`: nested JSON object representation grouped by anime/project folder and asset categories (`photo`, `thumbnails`, etc.).
4. **Presentation**:
   - Output formatted JSON inside `<pre id="output">` (2-space indentation).
   - Minimalist, dark-themed responsive UI with helper action buttons (Copy JSON, Refresh).
   - Informative error handling and loading indicators in `<pre>` when fetching or parsing data.

## File Changes
- Create `index.html` at the repository root.
