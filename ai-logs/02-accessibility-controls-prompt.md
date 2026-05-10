# AI Log 02 — Accessibility Controls and Voice Guidance

## Purpose of This Log

Record AI assistance related to voice guidance controls, repeat / pause / more detail / help actions, high contrast or low-vision settings, simplified interaction flows, and fallback behavior for BLV climbers.

## 1. Date / Project Stage

- Date: Week 7-9
- Project stage: High-Fi prototype refinement / accessibility interaction and fallback refinement
- Related portfolio/system section: User Requirements; Technical Implementation; Iteration / Before-and-After refinement; Evaluation & Reflection; Technical Reflection on AI-Assisted Development

## 2. AI Tool Used

- Tool name: Figma Make and OpenAI ChatGPT
- Model: Default model ChatGPT：GPT-5.5 Thinking 
- Access date: Apr. 29, 2026
- Link: https://www.figma.com/ai/ and https://chatgpt.com/

## 3. Intended Task

The AI interaction was used to support the design and front-end organization of HoldLight’s accessibility controls and voice-guidance recovery actions.

The goal was to make the core guidance flow more usable for blind and low-vision climbers. The interface needed to support short audio cues during climbing and give users clear recovery options when a cue was missed, unclear, or potentially unsafe. The key controls were:

1. Repeat cue.
2. Pause guidance.
3. Request more detail.
4. Ask for human help.
5. Adjust readable / low-vision settings such as text size and contrast.

Figma AI / Figma Make was used to explore the visual grouping of recovery controls, button hierarchy, and possible state variants. ChatGPT was used to refine labels, cue wording, and accessibility risks. AI did not decide the safety model, user requirements, or final accessibility priorities.

## 4. Prompt

Summarized design prompt:

"Help me refine the accessibility control panel for HoldLight, a mobile-first climbing support web app for blind and low-vision climbers.

Context:
The user receives short direction-first audio cues while climbing. If they miss a cue, feel uncertain, or need more information, the interface should make recovery actions easy to find and understand. The system should not rely only on visual icons, and it should not imply that automated guidance replaces human safety support.

Requirements:
- Keep the current scan → preview → climb flow.
- Design visible controls for repeat, pause, more detail, and human help.
- Suggest a Figma component layout for default, active, paused, repeated, more-detail, and help-request states.
- Support low-vision use with readable text, strong contrast, and large touch targets.
- Keep audio cue wording short and action-oriented.
- Avoid long explanation during active climbing.
- Include fallback states for uncertainty or low confidence.
- Keep human help available for safety-critical moments.
- Do not invent backend logic; focus on front-end structure, labels, states, and accessibility behavior.

Expected output:
Suggest a compact mobile control layout, button grouping, label wording, state variants, and example cue wording that can be manually reviewed against HoldLight’s user requirements."

## 5. AI Outcome

The AI suggested a mobile guidance control panel with a current cue area, large recovery buttons, readable labels, state variations, and a simplified hierarchy between current cue, recovery actions, low-vision settings, and human help.

### What worked

- The AI helped separate the default audio cue from optional recovery actions.
- The suggested repeat / pause / more detail / help structure matched HoldLight’s recoverable-interaction requirement.
- The output gave a useful starting point for grouping controls by urgency: immediate cue controls first, settings second, human help always available.
- Some label suggestions helped make actions clearer than icon-only buttons.
- The AI highlighted that audio guidance should be brief, consistent, and easy to repeat.
- The Figma-style state variants helped separate default guidance, paused guidance, repeated cue, more-detail request, and help-request states.
- The layout suggestions helped keep urgent recovery actions more visible than secondary settings.

### What did not work

- The first AI output felt too much like a generic fitness or navigation app.
- Some suggested controls were too small or too icon-dependent for low-vision use.
- Several labels were too vague, such as "Assist" or "Info", and did not clearly describe the user action.
- The AI did not fully account for the safety boundary between system guidance and human climbing support.
- Some suggested voice text was still too long for in-climb use.
- Some design suggestions still depended too much on visual grouping and needed clearer text labels.
- Some suggested state styles were visually subtle and might not be clear enough for low-vision users.
- The output needed manual review because automated confidence or route certainty cannot be assumed in real climbing conditions.

## 6. Team Action After AI Output

- Modified: We shortened default cue wording into direction-first prompts such as hand, clock direction, and coarse distance.
- Modified: We made repeat, pause, more detail, and human help visible as explicit recovery controls instead of hidden backup behavior.
- Refined: We kept controls readable through larger labels, stronger contrast, and simpler grouping.
- Refined: We treated text size, contrast, and low-vision support as part of the main accessibility workflow rather than optional decoration.
- Refined: We connected the controls to evaluation tasks that checked whether users could recover from uncertainty.
- Discarded: We removed vague or icon-only actions that could be hard to interpret.
- Discarded: We rejected wording that made the automated guidance sound fully reliable or safety-complete.
- Kept: We kept the basic recovery-control structure because it matched the user requirement for repeat, pause, more detail, and human help.

## 7. Verification Against User Requirements

- Requirement checked: Users should receive short, low-overload audio cues during climbing.
- Requirement checked: Users should be able to repeat, pause, request more detail, or ask for human support when cues are missed or uncertain.
- Requirement checked: The interface should remain readable and operable for blind and low-vision climbers.
- Manual test / walkthrough: We checked the flow from route preview into in-climb guidance and recovery actions.
- Manual test / walkthrough: We reviewed whether a user could find repeat, more detail, pause, and human help without searching through a dense menu.
- Accessibility check: We checked button clarity, text size, contrast, touch target spacing, and whether icon-only communication was avoided.
- Accessibility check: We reviewed whether key actions were understandable when audio or visual information was incomplete.
- Evidence used: User requirements in `user-requirements.html`, core feature documentation in `implementation.html`, alpha testing and refinement evidence in `evaluation-reflection.html`, and supporting screenshots in `assets/images/beforeafter/`.

## 8. Ethical / Accessibility / Reliability Considerations

- Possible risk: AI-generated controls may look clean visually but still be hard for BLV climbers to understand quickly.
- Possible risk: Automated route guidance may be interpreted as more certain than it really is.
- Possible risk: Long or delayed cues may interrupt climbing rhythm and increase cognitive load.
- Possible risk: Hiding fallback behind menus could make uncertain moments more stressful or unsafe.

- How the team reduced the risk: We treated AI output as a draft and checked it against HoldLight’s own user requirements.
- How the team reduced the risk: We kept human help visible and did not present the system as a replacement for belayers, coaches, or guides.
- How the team reduced the risk: We shortened cue wording and made more detail optional rather than the default.
- How the team reduced the risk: We manually reviewed controls for contrast, readability, touch size, and recoverability.

## 9. Final Use in Project

- Used in files/pages: `index.html`; `user-requirements.html`; `iteration-alternatives.html`; `implementation.html`; `evaluation-reflection.html`; `portfolio.css`; `portfolio.js`; `assets/images/beforeafter/cuebefore.png`; `assets/images/beforeafter/cueafter.jpg`; `assets/images/prototype/overview/hi-overview2.png`; `assets/images/hifi-ui.png`
- Final status: Used after manual revision and verification.
- Notes: This AI interaction supported accessibility-control layout, cue wording exploration, and recovery-state organization only. Final decisions about safety, fallback, and accessibility were made by the team using user requirements and testing evidence.
