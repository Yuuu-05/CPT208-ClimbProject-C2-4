# AI Log 04 — Responsive Debugging and Layout Fixes

## Purpose of This Log

Record AI assistance related to mobile-first layout fixes, image scaling, table responsiveness, navigation or interaction bugs, browser testing, and manual verification after debugging.

## 1. Date / Project Stage

- Date: Week 8
- Project stage: Final debugging / responsive layout refinement
- Related portfolio/system section: Portfolio website responsive behavior; Evaluation & Reflection; Technical Implementation; Iteration / Alternatives; Project Overview

## 2. AI Tool Used

- Tool name: OpenAI Codex and OpenAI ChatGPT
- Model: 5.5 Thinking；gpt-5.5
- Access date: Apr. 25, 2026
- Link: https://openai.com/codex/ and https://chatgpt.com/

## 3. Intended Task

The AI interaction was used to support responsive debugging of the HoldLight process portfolio.

The goal was to make the portfolio readable across desktop and mobile screens, especially where dense evidence tables, contribution tables, hero titles, testing evidence galleries, and image-heavy sections could overflow or become difficult to scan.

AI was used as a debugging and CSS-structure assistant. It did not decide the content, visual identity, or evaluation claims.

## 4. Prompt

Summarized debugging prompt:

"Help me debug the responsive layout of my HoldLight portfolio website.

Context:
The site has multiple HTML pages using one shared CSS file. Some sections contain large tables, testing evidence galleries, before/after screenshots, contribution tables, hero text, and mobile-first evaluation cards.

Problems to check:
- Evaluation tables overflow or become hard to read on mobile.
- The individual contribution table needs a readable mobile layout.
- Testing evidence images and copy panels should stack cleanly.
- Large hero titles and title shards should wrap without overlapping.
- Cards and screenshots should keep spacing and not push content off-screen.
- Motion-heavy sections should still work with reduced motion.

Requirements:
- Keep the existing visual style.
- Prefer CSS fixes and semantic table labels instead of rewriting content.
- Preserve real file structure and existing class names where possible.
- Use mobile breakpoints for tables, grids, hero titles, and evidence galleries.
- Do not remove evidence content.

Expected output:
Identify likely responsive issues and suggest scoped HTML/CSS/JS fixes that can be manually applied and then checked in browser-sized views."

## 5. AI Outcome

The AI suggested a set of scoped responsive fixes: convert dense tables into labelled stacked cards on small screens, add `data-label` support for table cells, constrain hero text widths, adjust grid breakpoints, improve evidence gallery stacking, and respect reduced-motion preferences.

### What worked

- The AI helped identify tables as the main mobile-risk area.
- The suggested `data-label` pattern matched the existing table content and made mobile rows easier to understand.
- The AI’s breakpoint suggestions helped guide CSS updates for evaluation cards, contribution tables, and evidence galleries.
- The output helped preserve the existing visual identity while improving readability.
- The reduced-motion reminder was useful for motion-heavy gallery and timeline sections.

### What did not work

- Some suggested CSS was too broad and could have affected unrelated pages.
- A few fixes assumed a component framework, but the project uses mostly static HTML, CSS, and vanilla JavaScript.
- Some generated breakpoints did not match the existing layout rhythm and needed manual adjustment.
- The AI could not verify visual appearance by itself; browser review was still necessary.
- Some table fixes needed real `data-label` values from the HTML, not generic labels.

## 6. Team Action After AI Output

- Modified: We added or preserved `data-label` attributes in dense tables so mobile table cards could show the original column meaning.
- Modified: We adjusted evaluation table behavior so desktop views keep table structure while mobile views become stacked readable blocks.
- Refined: We improved responsive behavior for alpha usability cards, testing evidence gallery panels, contribution table rows, and hero title wrapping.
- Refined: We constrained long text and allowed safer wrapping through CSS rules such as `overflow-wrap`, responsive grid changes, and mobile padding changes.
- Refined: We kept evidence images and tables in place rather than removing content to solve layout pressure.
- Discarded: We avoided broad global CSS resets that could damage other pages.
- Discarded: We rejected fixes that hid important evidence on mobile.
- Kept: We kept the mobile-first stacked-card approach for tables because it improved readability without changing the evidence content.

## 7. Verification Against User Requirements

- Requirement checked: The portfolio should be usable on mobile because HoldLight is presented as a mobile-first system.
- Requirement checked: Evaluation and implementation evidence should remain readable rather than being cut off by horizontal overflow.
- Requirement checked: Accessibility information should not disappear on small screens.
- Manual test / walkthrough: We reviewed the evaluation page sections that contain alpha testing, participants, tasks, results, and before/after evidence.
- Manual test / walkthrough: We checked the implementation contribution table and technical notes for mobile readability.
- Manual test / walkthrough: We checked project overview and navigation areas for text wrapping and visual overlap.
- Accessibility check: We checked whether stacked tables retained column labels through `data-label` text.
- Accessibility check: We reviewed reduced-motion behavior and avoided relying only on animated interaction to reveal information.
- Evidence used: Responsive CSS in `portfolio.css`, interaction logic in `portfolio.js`, and real table / gallery markup in `evaluation-reflection.html`, `implementation.html`, and `iteration-alternatives.html`.

## 8. Ethical / Accessibility / Reliability Considerations

- Possible risk: A visually polished desktop page may become unusable for mobile users if evidence tables overflow.
- Possible risk: Responsive fixes may accidentally hide content, especially limitations or safety notes.
- Possible risk: Animation-heavy sections may be uncomfortable or inaccessible for users who prefer reduced motion.
- Possible risk: CSS changes can create regressions across multiple pages because the portfolio uses one shared stylesheet.

- How the team reduced the risk: We scoped CSS selectors to page classes such as `.evaluation-page`, `.implementation-page`, and `.testing-iteration-page`.
- How the team reduced the risk: We kept evidence content visible and changed presentation rather than deleting material.
- How the team reduced the risk: We used labelled mobile table rows so content stayed understandable when columns collapsed.
- How the team reduced the risk: We preserved reduced-motion handling in the JavaScript and CSS where interactive evidence sections use motion.

## 9. Final Use in Project

- Used in files/pages: `portfolio.css`; `portfolio.js`; `index.html`; `implementation.html`; `iteration-alternatives.html`; `evaluation-reflection.html`; `testing-iteration.html`; `final-reflection.html`
- Final status: Used after manual responsive review and targeted revision.
- Notes: This AI interaction supported debugging strategy and responsive CSS planning only. Final breakpoints, selectors, and markup adjustments were checked against the actual portfolio pages.
