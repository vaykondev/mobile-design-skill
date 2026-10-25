# Screen recipes

Sizes in pt for a 402 × 874 iPhone frame (54 status bar, 34 home area). Top to bottom.
Side margin 20 everywhere unless the element is full-bleed.

## Onboarding (2 to 3 pages)

1. Media, full-bleed, top 560 pt, radius 0: a photo of the result the app gives (not the app UI).
   "Skip" top right over the media, text button with a soft text shadow.
2. Page bars: 2 pt tall, active 24 wide white, inactive 12 wide `track`, 6 apart. 24 below the media.
3. Title: display, 2 lines max, 20 below the bars. Say the benefit in 2 to 4 words ("Cinematic LUTs").
4. One line in body `textSecondary`, 8 below.
5. Spacer, then the primary button at the bottom ("Continue", last page "Get started").

## Paywall

1. Proof on top, 340 pt full-bleed: the user's own content before / after, split by a 2 pt white line,
   small labels in the bottom corners. Close (×) top left, 36 pt square on a scrim, visible immediately.
2. Title "<App> Pro" display; one line what free vs paid means.
3. Three benefits max: check icon + body text, 32 tall rows. No icons in circles.
4. Plans as rows 56 tall: selected = 2 pt white frame, other = 1 pt `track` frame. Name + badge
   ("Save 49%") left, price right in tabular semibold, the per-month or trial line under the name.
5. Primary button with the real action ("Try 7 days free").
6. Terms in caption `textSecondary`, centred, full sentence with the price after the trial.
7. Restore · Terms · Privacy as text buttons.

## Permission / empty state

App name small at top left, gear at top right. Big left-aligned display title in 2 lines ("Access
your videos"), one line of explanation, primary button at the bottom. No illustration, no icon in a circle.

## Grid gallery

Header: segment as two large words (titleLarge expanded, selected white, other `track`), sort and
settings icons on the right. Chips row for albums. Grid 3 columns, 1 pt gaps, radius 0, metadata on
the image bottom-left in caption semibold over a scrim, status badges top-right.

## List / settings

Title display left. Optional highlighted item on `surface` with one secondary button ("Upgrade").
Groups: section label + rows with lines. Values right in `textSecondary`. Toggles right. Version last.

## Editor with tool panel

Header 44: back, undo / redo centred, export as a 34 pt square outlined icon button on the right.
Media stage on black, as large as possible. Playback strip 48: play, timeline / trim strip, time in
tabular. Tabs as text (callout), active white with a 2 pt × 40 underline, separators above and below.
Panel fixed height (e.g. 216) for every tab: tiles 68 pt square with names under, selected = white
outline 2 pt offset 2; sliders as rulers with ticks, label left, value right.

## Bottom sheet

`surface`, top radius 6, grabber 36 × 5. Header row: Cancel left, title centre (headline), nothing
right. Rows: label, then a segmented control full width. Primary button at the bottom, a caption under
it with the consequence ("About 48 MB for 0:47").

## Progress and success

Progress: the media dimmed, a large tabular percentage, a thin 2 pt bar, Cancel as text button.
Success / Pro active: "Active" badge, huge two-line display title, the list of what is unlocked with
lines, renewal date in footnote, primary button that takes the user back to work ("Start editing").
