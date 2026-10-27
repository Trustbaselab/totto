# Totto — Design Specification

Full construction spec for the mark. Every number here is load-bearing; changing
one changes the silhouette at small sizes.

## Canvas

```
viewBox:      0 0 100 100
Safe area:    8 units on all sides
Stroke:       2.4 (head outline)
Fill:         none for outlines, solid for eyes/nose
Line cap:     round
Line join:    round
```

## Element 1 — Head

An ellipse with a **1.3 : 1** width-to-height ratio, bottom cut flat.

```
Horizontal extent:  13 → 87   (width 74)
Vertical extent:    22 → 78   (height 56)
Ratio:              74 / 56 = 1.32
Corner radius:      ~20 at top
```

**Why 1.3:1.** At 1:1 the head is a circle and reads as a ball. At 1.5:1 it reads
as a pancake. 1.3:1 is the narrow band where it reads as a *head* — wide enough to
feel grounded, tall enough to hold features.

**Why the flat bottom.** The bottom is a straight line, not a curve. This does two
things:

1. The mark appears to emerge from a surface rather than float. This is what makes
   it feel present rather than displayed.
2. It creates an anchor line, so the mark sits correctly on any background without
   needing a shadow, a bounding box, or manual optical adjustment.

## Element 2 — Ears

Round bulges integrated into the head outline — **not** separate circles.

```
Ear radius:       7
Position:         left at ~29,27 · right at ~71,27
Integration:      same continuous path as the head
```

**This is the single most important construction decision.** Separate `<circle>`
elements will read as **cat ears** at 16–24 px, because two overlapping outlined
shapes resolve into two bright blobs plus a gap. A continuous path keeps a single
silhouette at every size. Do not refactor this into circles.

## Element 3 — Eyes

```
Shape:            solid circle
Radius:           3.2
Position:         left 38,46 · right 62,46  (24 apart, both 24 below top of head)
Color:            solid, no outline
```

The blink animation scales the eye radius to 0.1 over 90 ms. Simple scale, no
complex easing — at small sizes any easing is invisible anyway.

## Element 4 — Nose

```
Shape:            inverted triangle
Width:            7
Height:           5
Position:         centred at 50,57
```

The inverted triangle is chosen because it is the only nose shape that is
distinguishable at 16 px. A rounded nose becomes a dot and is confused with the
eyes; a wide nose merges with the mouth area.

## Element 5 — Whiskers

```
Shape:            straight line, round cap
Length:           9
Angle:            ±28° from horizontal
Position:         left from 28,55 · right from 72,55
Stroke:           1.6
```

Two strokes only — one per side. More than two becomes visual noise below 32 px.

## Element 6 — Bottom edge

The flat cut at y = 78. This is not a separate element; it is the terminator of
the head path. It must remain perfectly horizontal.

## Scaling

| Size | What survives |
|---|---|
| 16 px | Silhouette + ears + eyes. Whiskers merge. Nose is a dot. **Still recognisable.** |
| 32 px | All six elements read. |
| 64 px + | Fully resolved. |

The mark was designed from 16 px upward, not from large downward. This is the
opposite of the usual order and it is the reason the small size works.

## Colour

The mark is monochrome by design. No gradient, no two-tone, no accent colour.

Reason: a mascot that depends on colour cannot appear in a single-colour context —
embossing, engraving, a favicon at 16 px, a black-and-white print. Monochrome
means it works everywhere, which is the entire purpose of a mark.

## Rejected versions

**v1-bear.svg** — round face, big ears, protruding snout. Rejected: generic.
It carried no visual relationship to anything else in the brand, and a generic
cartoon animal is less memorable than an ugly one.

**v2-otter.svg** — full body, tail, holding a data panel. Rejected: too complex.
At 32 px the tail and the panel both resolved into grey smudges. Documented here
so the rejection is not repeated.

---

*Trustbase Lab · 2026*
