# Natter avatar production standard — v1

Agreed direction: 26 November 2026. Brim is the presentation reference; Zeev V3 is the pixel-locked artwork production reference. The unified lab is a prototype, not a production account feature.

## Character contract
- Three colourways, three expressions (Friendly, Playful, Cheeky), three accessories (None, Scarf, Satchel): 27 complete artwork combinations per character.
- Preserve stable asset identifiers. Brim Friendly maps to the existing `gentle` filename token; do not rename the original art merely to change the visible label.
- Use transparent 512 × 512 masters. Preserve pose, scale, eye registration, silhouette, markings, detail and lighting; use controlled recolouring and fitted accessories without altering the approved expression or anatomy. Preserve original files; do not regenerate approved art to create a colourway.

## Shared interface
- Natter logo, rounded NatterNunito typography, navy/indigo background, Brim-style surfaces and controls. Use one shared renderer and configuration per character.
- Order: Character, character preview, Colour, Expression, Accessory. Keep the 27-combination development gallery separate from the main experience.
- Full art viewport: 220 CSS px logical art area, within a 232px stage, centred and contained. Verify perceived scale on-device; different silhouettes may need optical adjustment, not changes to the underlying image.
- One 48px circular chat preview, head and upper body; subtle 1px blue border at 35% opacity. Reserve bright blue outlines for active selection/status. No size choice in customisation. Other app contexts may use 32, 64 or 96px when appropriate.
- Brim reference portrait: scale 1.55, Flutter alignment (0.7, −0.72); browser equivalent image 155%, left −46.75%, top −7.7%.
- Zeev proposed final portrait: image 165.647059%, left −18%, top −7%. This moves the approved crop slightly upwards and left without zooming further. Pending visual comparison in the unified lab.
- Fixed per-character crop for all 27 combinations; never change crop based on expression, accessory or colour.
- Gentle 180ms crossfade for selection changes where appropriate; respect reduced motion. Character switching should not visibly slide or change the crop mid-transition. Validate the effect on device before app integration.
- Retain “Behind every character is a real person.” Avatar choices must not imply a behavioural score, friendship stage or status.

## Quality gate
1. Verify all 27 combinations load using the intended assets, with unchanged transparency and approved source geometry.
2. Compare all three expressions and accessories, check no unintended changes to eyes, markings, shadows, outline or accessory colours.
3. Compare 48px portraits across characters at the same viewport; check positioning, visible eyes and head/upper body, border and perceived size.
4. Test rapid selection changes, reduced motion, mobile layout and keyboard focus. Keep original labs as regression references.
5. Record user approval and any character-specific crop parameters before Flutter integration. No Firebase, account or identity persistence in this test lab. Local artwork caching in the browser is allowed for the test only.

## Development workflow
Prefer direct repository commits when permitted, otherwise complete replacement files, not line-by-line edits. Keep this document in the avatar lab repository and update it when a new shared rule is agreed. Future characters follow the same contract unless a deliberate exception is documented.
