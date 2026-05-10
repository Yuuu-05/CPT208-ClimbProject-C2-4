# AI Log 01 — Layered Route Preview UI

## Purpose of This Log

Record AI assistance related to the layered route preview UI, including Overview → Segment → Drill-down structure, mobile-first layout, route information hierarchy, and accessibility-friendly spacing / button structure.

## 1. Date / Project Stage

- Date: Week 5-6
- Project stage: High-Fi prototype refinement / route preview interaction refinement
- Related portfolio/system section: Route Preview UI; User Requirements; Iteration / Before-and-After refinement; Technical Reflection on AI-Assisted Development

## 2. AI Tool Used

- Tool name: Figma Make and OpenAI ChatGPT
- Model: Figma：Default model ChatGPT：GPT-5.4 Thinking 
- Access date: Apr. 10, 2026
- Link: https://www.figma.com/ai/ and https://chatgpt.com/

## 3. Intended Task

The AI interaction was used to support the layout exploration and interaction refinement of HoldLight’s layered route preview interface.

The goal was to translate our route-preview design requirement into a clearer mobile front-end and prototype structure. The interface needed to help blind and low-vision climbers understand a climbing route before starting, without presenting too much information at once. We wanted the route preview to support three levels of information:

1. Overview: a simple whole-route summary.
2. Segment: route information divided into smaller climbing sections.
3. Drill-down: optional detailed information when the user needs more guidance.

Figma AI / Figma Make was used to explore possible mobile frame structures, component grouping, and card hierarchy. ChatGPT was used to refine the information hierarchy and check whether the structure matched HoldLight’s accessibility goals. AI did not define the user requirement or the core design logic.

## 4. Prompt

Summarized design prompt:

"Help me explore a mobile-first layered route preview layout for HoldLight in Figma.

Context:
HoldLight supports blind and low-vision climbers. After wall scanning, the user needs to understand the route before climbing. The preview should use three levels: Overview, Segment, and Drill-down.

Requirements:
- Create a clear mobile frame structure.
- Use large readable text and strong visual hierarchy.
- Use card-based layout only if it reduces information overload.
- Show selected route, selected segment, and expanded detail states.
- Avoid decorative complexity.
- Keep buttons touch-friendly.
- Do not change the core user flow or invent new features.
- Keep accessibility in mind for blind and low-vision users.
- Do not make route guidance appear fully certain when uncertainty or human support may still be needed.
- Treat the output as layout exploration only.

Expected output:
Suggest Figma frame organization, component grouping, route card hierarchy, button placement, and possible interaction states for manual review."

## 5. AI Outcome

The AI suggested several Figma-style layout directions, including a route overview card, segment list, expanded detail panel, selected-state styling, and bottom action buttons. ChatGPT helped summarize these options into a clearer Overview → Segment → Drill-down route preview structure.

### What worked

- The AI output helped us quickly explore a clear visual hierarchy for route preview.
- The Overview → Segment → Drill-down structure matched our intention to reduce information overload.
- The card-based layout was suitable for a mobile-first interface.
- The suggested structure gave us a starting point for organizing route information before climbing.
- Some spacing and button suggestions were useful for making the interface easier to scan visually.
- The Figma-style frame structure helped us think about route preview as a progressive disclosure interface rather than a single dense information page.
- The suggested selected-state and expanded-detail patterns were useful for showing the difference between overview, segment, and drill-down information.

### What did not work

- The first AI output was too generic and looked like a normal fitness app interface.
- Some route descriptions were too long for a pre-climb context.
- The output focused too much on visual layout and not enough on blind and low-vision accessibility.
- Some buttons and labels were not specific enough for HoldLight’s climbing flow.
- The AI did not fully consider uncertainty, fallback, or the need for human support when route information may be unclear.
- Some Figma-style outputs were visually neat but did not fully address screen-reader or low-vision needs.
- Some visual hierarchy suggestions looked attractive but were too decorative for a safety-adjacent climbing context.
- The AI output could not be accepted directly because it was not based on our actual testing evidence.

## 6. Team Action After AI Output

- Modified: We reduced the amount of text in the route preview and made the information more direction-first and segment-first.
- Refined: We reorganised the layout so that the route overview appears first, followed by smaller route segments and optional details.
- Refined: We adjusted spacing, button size, and visual hierarchy to make the UI more readable on mobile screens.
- Refined: We changed generic labels into HoldLight-specific labels that better match the climbing guidance flow.
- Discarded: We removed overly decorative elements and UI parts that did not support route understanding.
- Discarded: We rejected wording that made the system sound fully certain about the route when uncertainty may still exist.
- Kept: We kept the layered structure because it matched our requirement to help users understand the route before climbing.
- Kept: We kept the card-based structure as a basic front-end layout pattern, but revised it manually.

## 7. Verification Against User Requirements

- Requirement checked: Route preview should help users understand the route before climbing.
- Requirement checked: The interface should reduce cognitive load by presenting information in layers.
- Requirement checked: The UI should support mobile use with readable text, clear buttons, and simple interaction steps.
- Manual test / walkthrough: We checked whether a user could move from wall scan to route preview, read the overview, open a segment, and access more detailed route information without getting lost.
- Manual test / walkthrough: We reviewed the flow on a mobile-sized screen to check text wrapping, button spacing, and visual hierarchy.
- Accessibility check: We checked whether the interface avoided dense text, unclear labels, small touch targets, and information overload.
- Accessibility check: We reviewed whether key information was understandable without relying only on visual decoration.
- Evidence used: User requirements from our portfolio, route preview before/after refinement, BLV-related accessibility goals, and manual mobile walkthrough results.

## 8. Ethical / Accessibility / Reliability Considerations

- Possible risk: AI-generated UI may look visually attractive but still be difficult for blind or low-vision users to understand.
- Possible risk: The interface may accidentally make route guidance appear more certain than it actually is.
- Possible risk: Too much route detail before climbing may increase cognitive load instead of reducing it.
- Possible risk: Generic AI-generated wording may not match the safety needs of BLV climbers.

- How the team reduced the risk: We treated the AI output as a draft, not as final design evidence.
- How the team reduced the risk: We manually revised the information hierarchy to prioritise clarity, route understanding, and reduced overload.
- How the team reduced the risk: We preserved fallback and help options for cases where route information is unclear.
- How the team reduced the risk: We checked the UI against HoldLight’s own user requirements rather than accepting AI suggestions directly.

## 9. Final Use in Project

- Used in files/pages: `index.html`; `user-requirements.html`; `iteration-alternatives.html`; `implementation.html`; `evaluation-reflection.html`; `portfolio.css`; `portfolio.js`; `assets/images/prototype/overview/hi-overview2.png`; `assets/images/hifi-ui.png`
- Final status: Used after manual revision and verification.
- Notes: This AI interaction supported layout exploration, prototype scaffolding, and UI structure only. Final route preview logic, user requirement interpretation, and accessibility decisions were made by the team.
