# README Medal Links Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a top-right medal strip to the GitHub profile README and route medal clicks to a lower `Profile Links` section.

**Architecture:** Update `README.md` with a right-aligned HTML table containing the three medal images, each anchored to the in-page `#profile-links` section. Add a `## Profile Links` section further down containing the three requested external URLs.

**Tech Stack:** Markdown, GitHub README HTML rendering

---

### Task 1: Update README layout and links

**Files:**
- Modify: `README.md`
- Create: `docs/superpowers/specs/2026-03-28-readme-medal-links-design.md`
- Create: `docs/superpowers/plans/2026-03-28-readme-medal-links.md`

- [ ] **Step 1: Write the failing content expectation**

Expected README behavior:
- Three medal images appear in the top-right area.
- Clicking any medal jumps to `## Profile Links`.
- `## Profile Links` contains GitHub, Khan Academy, and HackerRank links.

- [ ] **Step 2: Inspect current README to verify the behavior is missing**

Run: `rg -n "Profile Links|output_1|output_2|output_3" README.md`
Expected: no matches

- [ ] **Step 3: Write the minimal implementation**

Add a right-aligned HTML table near the top of `README.md`:

```md
<table align="right">
  <tr>
    <td><a href="#profile-links"><img src="./medals/output_1.png" height="180" alt="Medal 1" /></a></td>
    <td><a href="#profile-links"><img src="./medals/output_2.png" height="180" alt="Medal 2" /></a></td>
    <td><a href="#profile-links"><img src="./medals/output_3.png" height="180" alt="Medal 3" /></a></td>
  </tr>
</table>
```

And add:

```md
## Profile Links

- [GitHub](https://github.com/venkateshwarreddyr)
- [Khan Academy](https://www.khanacademy.org/profile/venkateshwarreddyr/)
- [HackerRank](https://www.hackerrank.com/profile/venkateshwarredd)
```

- [ ] **Step 4: Run verification checks**

Run: `rg -n "Profile Links|output_1|output_2|output_3|khanacademy|hackerrank|github.com/venkateshwarreddyr" README.md`
Expected: matches for all inserted content

- [ ] **Step 5: Commit**

```bash
git add README.md docs/superpowers/specs/2026-03-28-readme-medal-links-design.md docs/superpowers/plans/2026-03-28-readme-medal-links.md
git commit -m "feat: add README medal links section"
```
