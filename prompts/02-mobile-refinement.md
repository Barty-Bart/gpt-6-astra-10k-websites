MOBILE EXPERIENCE — REQUIRED

Design mobile as an intentionally composed experience within the same website and codebase. Adapt navigation, typography, spacing, animation framing, and scroll timing for small screens.

1. PERSISTENT MOBILE NAVIGATION

Keep a compact navigation bar fixed to the top of the viewport throughout the entire website, including after the visual story ends.

Place the brand symbol and wordmark on the left and a hamburger menu on the right. Both must remain visible while scrolling.

Mount the navigation outside the pinned animation section so it cannot disappear when that section ends. Ensure its stacking order keeps it above the animation and page content.

Use a branded background with sufficient contrast. Respect phone safe-area insets and provide at least 44 × 44 px touch targets.

The hamburger must open an accessible menu with clear navigation links, a close button, keyboard support, focus management, and Escape-to-close behavior. Close it after selecting a link.

Offset anchor destinations so the fixed header does not cover section headings.

2. MOBILE HERO COMPOSITION

Prioritize the animated visual. Keep the opening screen simple:
- Persistent brand navigation.
- One short headline.
- One primary action.
- A subtle scroll cue.

Remove or shorten supporting paragraphs, decorative labels, and secondary actions when they compete with the visual.

Position text in deliberate negative space. Keep the main subject, headline, and action clear of each other and of the fixed navigation.

During the main animation, allow the imagery to occupy the screen without unnecessary text overlays. Reintroduce concise copy and an action at the final product reveal.

3. DEDICATED PORTRAIT ANIMATION

Continue with the provider selected for the desktop build: Higgsfield MCP by default, or fal.ai MCP when explicitly requested. Verify its portrait-generation tools and live model schema before submitting. If the required tools are unavailable, explain the gap and continue independent layout work; do not silently switch providers.

For a cinematic image-sequence website, create a dedicated portrait animation for mobile alongside the landscape desktop version.

Generate portrait source images and connected animation clips in approximately 9:16. Recompose the scene for a tall screen rather than stretching landscape footage.

Preserve the same brand, product geometry, logo, label, palette, lighting, material quality, and narrative across both versions.

Keep important action within the central portion of the portrait frame, allowing for cropping on phones with different aspect ratios.

Reserve space for navigation at the top and for copy where needed. In the final product shot, position the product so it remains fully visible above the headline and action.

Use a continuous environment that fills every edge. Reject visible seams, borders, rectangular panels, or mismatched backgrounds that make the animation look pasted onto the page.

Use the exact final frame of one clip as the starting reference for the next. Inspect connections for jumps in composition, lighting, scale, and object placement.

Check the actual generated output against the intended motion. If a required camera movement is missing, correct it or supplement it carefully in the renderer. Rotations must never expose empty corners.

4. MOBILE SCROLL PACING

Tune mobile scroll timing independently from desktop.

Keep the story moving with normal thumb gestures. Compress inactive holds, especially moments where objects have landed but the next transformation has not started.

Preserve smooth motion through falling, landing, spinning, zooming, and product reveal. Adjust the scroll-to-frame mapping before removing frames; removing frames alone does not shorten the scroll distance.

Use brief opening and closing holds so visitors can read the headline and recognize the product.

Keep macro transitions visually sharp when the intended effect is extreme magnification rather than blur.

Provide a visible way to skip the story and reach the main content.

5. RESPONSIVE ASSET DELIVERY AND PERFORMANCE

Store both animation variants, but select the appropriate version before requesting animation frames.

Mobile must request only the portrait sequence. Desktop must request only the landscape sequence. Do not preload both and hide one with CSS.

Use responsive image selection for posters and other large supporting imagery as well.

If the viewport crosses the breakpoint, cancel obsolete requests and release decoded images from the previous sequence.

Show a lightweight poster immediately. Load frames progressively around the current scroll position, prioritizing the frame the visitor needs now.

Limit simultaneous requests and decoded-image memory. Use compressed WebP or an appropriate supported format, sensible image dimensions, and a tested frame rate.

For a comparable sequence, 720 × 1280 at around 18 fps is a starting point for mobile, not a universal requirement. Choose final settings through visual inspection and measured file sizes.

Do not block the page until the entire sequence downloads. Keep the rest of the site usable while media loads.

Respect reduced-motion preferences by showing a composed still and normal page flow without fetching the animation sequence.

Provide a usable poster fallback if animation loading fails.

6. MOBILE VALIDATION

Preview the actual implementation at several phone widths and heights.

Inspect:
- Opening composition and immediate readability.
- Fruit or object motion staying within the frame.
- Clip boundaries and background continuity.
- Scroll pacing through landing and transformation.
- Rotations and zooms without exposed edges.
- Final product visibility and readable branding.
- Text and buttons staying clear of the subject.
- Persistent navigation after the animation ends.
- Menu opening, closing, focus behavior, and anchor offsets.
- Safe-area spacing and absence of horizontal overflow.
- Reduced-motion and loading-failure behavior.

Check desktop again after mobile changes.

Verify that each viewport requests only its intended animation assets when network inspection is available. Report measured asset sizes separately from actual loading-speed measurements; do not promise speed based on file size alone.

Leave a mobile preview available for review and explain that mobile and desktop are responsive versions of the same website, with different animation assets selected automatically.