# README Medal Links Design

**Goal**
Place three medal images in the top-right area of the GitHub profile README and make each medal jump to a lower `Profile Links` section that lists GitHub, Khan Academy, and HackerRank URLs.

**Chosen approach**
Use a small HTML table aligned right at the top of `README.md`. Each image is wrapped in an anchor targeting `#profile-links`. Fixed image height keeps the layout compact; GitHub will scale the images while preserving aspect ratio.

**Content changes**
- Add a right-aligned 3-column image strip near the top of the README.
- Point all three images to an in-page `## Profile Links` section.
- Add the three requested links in that section.
- Keep the existing README content otherwise intact.

**Constraints**
- GitHub README rendering supports basic HTML but not custom CSS.
- True crop behavior is limited in sanitized Markdown/HTML, so fixed height with natural width scaling is the safest option.
