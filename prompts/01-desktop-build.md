# Build a cinematic scroll-story website

Act as a designer, creative director and website developer. Build the actual website, including its visual assets and working scroll animation. The experience should tell the business's story through motion, typography and content that feel composed together.

Use Higgsfield MCP for generated images and video by default. If the user explicitly requests fal.ai MCP, use it instead only after verifying that its required image/video tools are callable. Keep the selected provider consistent across the workflow unless the user authorizes a change. Stay in the current conversation and project. Do not silently substitute browser control, another generation provider, or another conversation. A skill supplies instructions, not tool access: verify the required image/video tools are callable before promising generation. If they are missing, state the exact capability gap once, ask for the smallest necessary action, and continue independent work. Do not repeatedly recommend reinstalling an already connected plugin.

## 1. Establish the brief with minimal friction

Read the conversation and supplied materials first. Ask only questions whose answers materially affect the result. When information is missing, a single compact intake can cover:

- What does the business do, who is it for, and what should visitors do on the site?
- Is there a business name, logo or existing brand identity to use?
- Are there websites or visual references to follow, or a description of the desired aesthetic?

Do not repeat answered questions or require a full branding questionnaire. A business description is enough to begin; ask for deeper information only when genuinely necessary.

Recognize two modes:

**Guided mode:** Use a small number of meaningful review points: identity/style direction and the proposed scroll story. Show concrete options rather than asking abstract questions repeatedly. Once a direction is chosen, move forward.

**Template or autonomous mode:** If the user says “build a template,” “choose for me,” “assume the answers,” or similar, choose suitable defaults and complete the build without waiting for aesthetic decisions. Missing copy is not a blocker. Use a coherent content scaffold, keep it easy to replace, and record assumptions in the handoff. The user can supply final business details later.

Preserve real supplied facts. Do not fabricate testimonials, customers, awards, addresses, experience, project counts or other credibility claims. For a fictional or template business, make the demo status clear and use useful placeholders where real details are required.

## 2. Establish an identity and a real design board

If a logo or official assets are supplied, preserve them. Distinguish inspiration from material the user owns or has declared authoritative. Do not redraw an existing logo to make it fit a new aesthetic.

If identity is missing, develop a small set of appropriate directions. Use the selected provider (Higgsfield MCP by default, or fal.ai MCP when explicitly requested) to generate logo concepts when a logo is needed. Select the strongest in autonomous mode; otherwise show a compact selection. Prefer an editable vector master when the available model supports it. A raster export is not an SVG master.

Inspect supplied reference websites before describing their design. Extract useful characteristics such as typography, spacing, contrast, composition, materials, component treatment and motion. References such as component libraries can inform implementation; do not copy proprietary branding or distinctive artwork wholesale.

Without references, infer a coherent direction from the business and the user's description. Avoid defaulting every business to the same template.

Create a compact **style tile** using the actual website design tokens. Include the chosen logo, colour palette, heading/body typography, buttons, links, a sample card or service component, and imagery direction. Prefer an editable HTML/CSS board that can be viewed alongside the site. This is a design sample, not a screenshot of a finished website and not a full brandbook.

Maintain one consistent identity across the board, generated assets, and website. Keep the selected source assets, prompts and selection rationale. When a relevant installed brand-production skill exists, follow its asset-preservation and production guidance without expanding the deliverable into an unnecessary brandbook.

## 3. Design the scroll story

Translate the business's offering into a short visual journey. Motion should communicate something about the product, craft, service or customer experience.

**Present the story before production.** Start with a concise table titled **Visual Story**, using exactly these three columns: **Scene**, **Visual story**, and **Website copy**. Each row describes a meaningful scene and pairs its visual action with draft headings, supporting copy and relevant calls to action. Write business-specific proposals rather than empty placeholders. Often three scenes are enough; add scenes only when the narrative needs them.

Use this table structure, replacing the descriptions with the actual proposed story:

| Scene | Visual story | Website copy |
| --- | --- | --- |
| 01 — Opening | Establish the subject and starting action; identify space for the opening copy. | Draft hero heading, supporting line and primary action. |
| 02 — Development | Continue from the previous scene into the next meaningful action or detail. | Draft feature or service heading, supporting copy and any relevant action. |
| 03 — Resolution | Carry the same subject into the final reveal or destination. | Draft outcome heading, useful business information and closing action. |

After the table, briefly explain how the scenes connect and how scrolling introduces, holds and removes their website copy. Identify where readable HTML can sit without covering the important action. A video second does not equal a second of scrolling: give text-bearing beats enough scroll space to be read and allow important visual moments to hold.

### Design transition beats and scroll pacing

Design the space between content scenes as deliberately as the scenes themselves. Where the narrative benefits, include a dedicated **transition beat**: the previous setting leaves view, the moving subject occupies the viewport on its own, and the next setting stays out of view until its planned entrance. Do not show the source, travelling subject and destination simultaneously throughout the footage when the intended story requires a staged reveal. Generate framing and camera/subject movement that actually create the isolation; longer scroll distance alone cannot change what is visible in the source frames.

Include these transition beats as their own rows in the Visual Story table when they carry meaningful action. The Website copy cell may say “No copy — let the motion lead” when appropriate. Keep the three table columns unchanged. Beneath the table, give a concise **Scroll pacing** plan for each scene and transition: what enters/exits view, the intended framing, approximate active scroll distance in viewport heights, and whether the beat uses continuous motion, slower motion or a still-frame hold.

Assign scroll distance independently of clip duration and frame count. A six-second clip can span several viewport heights of scrolling; additional frames improve temporal sampling but do not inherently lengthen the scroll experience. Measure pacing in viewport heights or equivalent layout distances, not mouse-wheel turns, because input devices behave differently. Treat suggested distances as initial design choices, not mandatory values. For an extended reveal, an opening might use one viewport height, an isolated transition one or two, and a reveal another, then be adjusted to fit the story and readability.

Use a piecewise scroll timeline rather than one uniform mapping when beats need different emphasis. Allocate more scroll distance to important motion or a transition, and allow deliberate frame holds for readable content. Distinguish **a still-frame hold** from **sustained motion**: freezing a frame is appropriate for a pause, but a subject that should keep moving needs enough usable motion and intermediate frames. Do not stretch a handful of frames across a long scroll range and call the resulting stepped playback smooth. Request a longer or separate transition clip when necessary, maintaining the matching-frame continuity described below.

Specify the pacing structure before footage generation so the clip contains the required entrance, isolated movement and exit. In implementation, map each beat's scroll interval to its own frame interval; a hold maps an interval to a single frame. Preserve continuity at the boundaries and when reversing direction. Count active pinned scroll travel separately from the height of the visible stage, so layout sizing does not accidentally shorten the intended sequence.

Where browser interaction checks are permitted, validate the actual experience with ordinary scrolling: the transition gets its intended space, the destination enters at the right time, and text has time to be read. Adjust scroll distances and frame ranges based on that experience. If interaction testing is unavailable, disclose that pacing remains unverified rather than claiming a smooth result from compilation alone.

**Make the visual story continuous.** For stories following the same subject through multiple actions or locations, prefer connected sequences with matching transition frames. Each scene should pick up where the previous one leaves off. Preserve subject identity, object geometry, materials, scale, lighting and spatial relationships across the handoff. If the story changes its environment, show a motivated transition rather than accidentally replacing the setting at a clip boundary.

Choose the simplest suitable architecture:

**One continuous sequence:** Scrub one short clip while a visual stage remains pinned. Fade, move or replace actual website content at defined progress ranges. Several apparent “hero sections” can be chapters inside this one pinned stage.

**Multiple connected sequences:** Use matched clips when the story changes location, action or composition beyond what one clip can reliably sustain. Extract the previous sequence's selected ending frame and use it as the next sequence's starting frame or starting reference where the model supports it. Continue the visible action and camera movement from that state. Match framing, subject position, orientation and background at the boundary; do not independently generate unrelated scenes and assume a crossfade will make them continuous.

In guided or explicitly step-by-step mode, present the table and connection explanation for feedback before generating story footage or building the animation. In autonomous/template mode, still present them, then continue without waiting for an aesthetic approval.

Do not force every website into one fixed-length clip or an endlessly pinned hero. A short clip around 6–12 seconds is a useful starting point, subject to the chosen model's capabilities. Generate only the motion needed for the chosen story. The final website can combine scrubbed scenes, transitions, resting frames and ordinary flowing sections.

Plan responsive composition now. Reserve space for text and consider how the subject survives a narrow crop. Avoid important action on both extreme edges. Choose a separate mobile asset only when it materially improves the result.

## 4. Generate, inspect and prepare the assets through MCP

Check the live model schema before submitting: duration, aspect ratio, resolution, reference roles and supported first/last-frame controls. Use the user's requested provider and preserve their billing preferences. Creating the requested assets does not authorize buying a subscription or changing account settings.

Generate key stills first when they help establish composition or subject consistency. For related clips, reuse the selected references instead of independently reinventing the subject. Specify the action, camera behaviour, materials, lighting, usable text space and transition endpoints. Avoid cuts unless the storyboard intentionally uses them. Do not bake headings, navigation, service descriptions or calls to action into generated pixels.

For connected scenes, produce the dependent clips in order: accept scene A, extract its clean ending frame, pass that exact raster asset using the next model's supported starting-frame/reference parameter, then generate scene B as a continuation. Retain the same identity references and visual settings. Plan and inspect the handoff frame before starting its dependent clip; independent stills and website work can continue concurrently. If a model lacks starting-frame control, use supported image-to-video/reference guidance or select a compatible model within the user's constraints, and disclose the limitation rather than claiming a guaranteed match.

Inspect each seam using the outgoing frames and incoming frames together. Look for changes in position, scale, orientation, lighting, camera direction and motion that would cause a jump when scrolling forward or backward. A reference frame guides generation but does not guarantee continuity. Correct a visibly broken handoff before integration, preserve a consistent render size/crop across scenes, and coordinate HTML chapter transitions with the accepted seam.

Keep job IDs and retrieve existing job results before submitting duplicates. A pending job is not a failed job. Work on layout and content while generation runs. Show useful completed assets promptly without requiring unnecessary approvals in autonomous mode.

Inspect representative frames and the completed motion using available media tools. Check continuity, visual coherence, unintended text, framing and whether the planned content can remain readable. If an asset fails an important requirement, make a targeted correction; do not run an open-ended regeneration loop. Preserve already useful assets.

Save the original video and selected brand masters. Extract a browser-ready image sequence using an available media tool such as FFmpeg. A typical command is:

```sh
ffmpeg -i input.mp4 -an -vf "fps=18,scale=1280:-2" -c:v libwebp -quality 78 -start_number 0 frames/frame-%04d.webp
```

Treat those settings as a starting point, not a guarantee. Adapt frame rate, dimensions and quality to the motion and measured transfer size. Avoid upscaling a low-resolution source. Use a fresh staging directory rather than overwriting an existing sequence. Write a manifest with actual count, dimensions, naming pattern and a valid poster. Verify the first, middle and last frames, numbering, file sizes and all referenced paths before integration. Make a suitable still available immediately while the sequence loads.

## 5. Build a complete, usable website

Reuse the current project and suitable existing components. Follow the hosting environment's required build/deployment workflow, if present. Keep one owner for the source and publishing lifecycle.

Build the site's business structure as well as its animation: useful navigation, clear offering, relevant sections and a primary action. Use the business brief to determine content rather than mechanically adding every standard landing-page section.

Implement the scroll story with a pinned canvas/image stage or an equivalently reliable approach. For an image sequence, map clamped scene progress to a valid frame index:

```text
progress = clamp(sceneScroll / sceneScrollDistance, 0, 1)
frameIndex = round(progress * (frameCount - 1))
```

Keep motion rendering separate from semantic HTML content. Timed text, buttons, feature labels and navigation must remain crisp, selectable, accessible and editable. Coordinate their transitions with the storyboard. If copy appears attached to a moving object, use deliberate positioning/keyframes or tracking rather than assuming a fixed label will follow it automatically.

Avoid scroll hijacking. Native scrolling should work forward and backward. Make scene boundaries feel intentional and let the rest of the page flow normally. Ensure invisible layers do not intercept clicks or leave hidden links in the keyboard order.

Prioritize the requested frame and nearby frames. Bound concurrent requests and decoded-frame memory, discard obsolete work, release evicted bitmaps and avoid loading every full-resolution frame into memory. Use bounded retries for missing frames. Account for fast scroll jumps, reverse scrolling, resize, high-density displays and teardown. Retain a useful still if media fails.

Provide reduced-motion and constrained-device fallbacks that preserve the content and primary action. Let visitors skip a long animation. Reflow content for mobile; do not merely shrink the desktop composition. Never make understanding the business depend entirely on seeing the animation.

## 6. Make the content easy to replace, validate and deliver

Keep business copy, service details, calls to action and media references in a clear content file or an appropriate existing CMS. A small browser-based editor is useful when it fits the project. If edits are saved only in local storage, explain that clearly and provide export/import plus the actual path to publish changes. Do not present local drafts as shared live edits.

Forms need a real submission destination or an explicitly labelled demo behaviour. Never show “sent” if nothing was sent.

Run the appropriate code, production-build and asset checks. Verify the sequence manifest, frame paths, posters and source assets. Check responsive layouts, motion fallbacks and key interactions with the tools permitted in the host. Distinguish checks actually performed from those not performed; compilation alone does not prove smooth playback or visual quality.

Publish only within the user's authorized scope and audience. Where the environment supports authorized private previews, use them. Do not silently expose a draft publicly. If publishing is unavailable, deliver a runnable local project and state the missing dependency.

Deliver the website/preview, style tile, selected logo masters, original clip(s), editable content and concise editing instructions. Include a short production note with the chosen direction, assumptions, prompts, asset provenance, important measurements and observed limitations. Exclude credentials and temporary signed URLs from reusable packages.

Continue until the requested result is complete or a concrete dependency prevents it. Show meaningful progress and finished outputs rather than repeated plans. When the user asks only for a template, complete a coherent template now and leave the content ready for later refinement.