# The default AI look, and what to do instead

Taken from Tona's own first version, which had every item on this list. Each row: what the model
reaches for, why it reads as generated, the replacement.

| Default | Why it looks generated | Instead |
|---|---|---|
| Pink/purple gradient background | Every AI app demo uses it; it fights the content | Flat `background`; colour comes from the content |
| Gradient primary button | Looks like a template CTA | Solid accent, radius 2, expanded type |
| Glass cards over a gradient | Low contrast, muddy, dated | Rows with 1 pt lines; `surface` only for sheets |
| Pills everywhere (buttons, chips, segments) | Default Material 3 / Tailwind `rounded-full` | Radius 2 for all controls |
| Icon in a coloured circle on each row | Settings-template look, adds noise | Plain stroke icon or no icon; the label is enough |
| Crown / sparkles / diamond for Pro | Cliché for "premium" and "AI" | The word Pro in a badge; show the real result instead |
| Emoji as icons | Inconsistent across platforms, childish | One stroke icon set |
| Everything centred | Feels like a landing page, wastes width | Left-aligned titles and text, bottom button |
| Phone mockup inside onboarding | A picture of the app inside the app | A full-bleed photo of the result the user will get |
| "Before / after" with fake content | Gives nothing to believe | Before / after on a real-looking frame, with a labelled divider |
| Tab bar with 2 tabs | A whole bar for one extra screen | Root screen + one icon in the header (gear → settings) |
| Shadows and glows on dark | Invisible or dirty on black | Separate with lines and grey levels |
| Several accents / colour per category | No hierarchy, toy look | One accent; categories differ by label, not colour |
| Cards inside cards | Box noise, lost margin | One level of grouping |
| Gradient placeholder instead of media | Screams "mockup" | Real or generated photos with one shared style |
| 3 to 5 font sizes per row, many weights | Busy | 3 text levels, 2 weights |
| Thin grey 10 pt captions | Unreadable, fails contrast | Minimum 11 pt, `textSecondary` 8:1 |
| Marketing copy ("Unlock your creativity") | Says nothing | Plain verbs: "Export video", "Try 7 days free" |
| Light and dark both, both half done | Twice the screens, half the care | One theme finished; add the second later |
| Big rounded 24 pt cards | "Friendly" template | Radius 0 / 2 / 6 only |

## Quick test

Cover the logo. If the screen could belong to any app, it is still generic. The content (their photo,
their numbers) and one strong type decision should make it recognisable.
