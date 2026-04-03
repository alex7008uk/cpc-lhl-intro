# Photo Display Design

**Date:** 2026-04-03  
**Status:** Approved

## Context

The existing bio card displays a portrait photo (`images/lhl.png`) in a right-side column. The current implementation has two issues:
1. The photo column (255px) is narrower than desired — the full-photo editorial style lacks visual presence.
2. On mobile, the photo renders as a full-width horizontal banner crop (220px tall, `object-position: center 20%`), which the user found visually awkward.

The goal is to give the photo more weight on desktop while replacing the mobile banner with a cleaner circular avatar layout.

## Decisions

### Desktop (> 680px)
- Photo column width: **300px** (was 255px)
- Gradient overlay on `.bio-photo::after`: replace the existing subtle blend with a stronger white-to-transparent fade from the left edge:
  ```css
  background: linear-gradient(to left, transparent 50%, rgba(255,255,255,.75) 100%);
  ```
- `object-position` stays `top center`

### Tablet (≤ 680px)
- Photo column width: **200px** (was 170px)

### Mobile (≤ 520px)
- Remove the full-width horizontal photo strip (`.bio-photo { width: 100%; height: 220px }`)
- Replace with a **72px circular avatar** embedded in the `.bio-identity` header row
- Avatar sits left of the name/title block, aligned to the top
- Avatar styling: `border-radius: 50%`, `border: 2.5px solid var(--gold)`, subtle box-shadow
- Remove the mobile-specific `.bio-photo::after` gradient override (no longer needed)

## Files to Modify

- `index.html` — all changes are CSS only, within the existing `<style>` block and the `.bio-identity` HTML fragment

## Verification

1. Open `index.html` in a browser at desktop width (> 680px): photo column should be wider with a noticeable soft left-edge blend.
2. Resize to ~600px (tablet): photo column narrows to 200px, layout remains side-by-side.
3. Resize to < 520px (mobile): horizontal photo strip is gone; a 72px circular avatar appears left of 林夏蘭's name and title.
4. Confirm no layout breakage at 460px (the smallest breakpoint).
