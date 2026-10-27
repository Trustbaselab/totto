# Totto

**The mascot of Trustbase Lab. Trust + Otter + Bot.**

![Totto](assets/v3-totto.svg)

---

## The name

**Totto = Trust + Otter + Bot.** 托托 (tuō tuō) in Chinese.

Three things in one word, and each of them is a decision:

- **Trust** — the reason the company exists. Not "data," not "AI" — trust.
- **Otter** — the animal. Otters are a deliberate choice, explained below.
- **Bot** — the form. It is a machine, and it does not pretend otherwise.

The doubling in Chinese (托托) is not decoration. Reduplication is how Mandarin
makes a name feel affectionate and small — 猫猫, 狗狗, 宝宝. A mascot that sounds
like a diminutive is a mascot people will talk about. The name is a tool, and it
was chosen to be easy to say out loud.

---

## Why an otter

Because every technology company picks a predator, and we did not want to.

The default mascot is something that hunts: a falcon, a wolf, a shark, a tiger.
The metaphor is speed and aggression, and it is a metaphor about **taking**. It is
also, after fifteen years of it, completely invisible — a wolf says nothing
because every company has a wolf.

An otter is different in one specific way that matters to us. **Otters hold on to
things.** They carry a favourite stone for their whole life. They lie on their
back and keep what they found. When the water moves, they are not faster than it —
they are *anchored* in it.

That is the correct metaphor for what we build. We are not trying to outrun the
information flood. We are trying to **hold on to what is true** while it moves
past. An otter is the animal of retention, not of pursuit.

There is a second reason, less flattering and more honest: otters are
**unthreatening**. Nobody is afraid of an otter. A company that sells data
infrastructure to governments and industry associations should not present itself
as a predator. It should present itself as something that will not let go.

---

## The design

### Version history

Three versions were drawn. Two were rejected, and the reasons matter more than
the final result.

**v1 — a bear.**
Round face, big ears, protruding snout. Rejected because it shared no visual
language with anything else we were making. It was a generic cartoon animal, and
generic is worse than ugly — ugly is memorable, generic is not.

**v2 — a full otter.**
Whole body, tail, and a small data panel it held up. Rejected for a simple
reason: **it was too complex to survive small sizes.** At 32 px the tail became a
smudge and the data panel became a grey blob. A mascot that only works when it is
large is a mascot you cannot actually use.

**v3 — a minimal half-head.**
This is the one we kept. Six elements, drawn from a single continuous path where
possible.

### The six elements

| # | Element | Construction |
|---|---|---|
| 01 | Head | One ellipse, aspect ratio **1.3 : 1** — wider than tall |
| 02 | Eyes | Two solid dots, animated to blink |
| 03 | Nose | One inverted triangle |
| 04 | Whiskers | Two short diagonal strokes, left and right |
| 05 | Bottom edge | **Cut flat** — it is half a head, emerging from the desktop |
| 06 | Ears | Two round ears, **continuous with the head outline** rather than added on |

### The two decisions that define it

**Decision 1 — it is half a head, not a whole head.**

The bottom is cut flat, as though the creature is emerging from the surface. This
is not a stylistic flourish; it is what makes the mark feel *present* rather than
*displayed*. A complete head is a picture. A half head is an appearance.

It also solves a practical problem: cutting the bottom means the mark has a
natural anchor line, so it sits correctly on any surface without needing a shadow
or a bounding box.

**Decision 2 — the ears are part of the outline, not added to it.**

The ears are drawn as bulges in the same continuous path as the head, not as
separate circles placed on top. The difference is subtle at full size and
decisive at small size: separate circles read as **cat ears** at low resolution,
because the two overlapping shapes separate into two bright blobs. Continuous
ears stay a single silhouette.

This is why the final asset is a single `<path>` rather than a composition of
`<circle>` elements.

---

## Why so minimal

Three precedents were examined: **Alibaba**, **JD.com**, and **Grok Bot**. All
three marks are radically simple, and all three were designed by people with the
resources to be complex. That is the signal.

The reason is not aesthetic preference. It is that **complexity becomes noise at
small sizes.** A logo with eleven elements reads correctly at 256 px and reads as
a grey rectangle at 16 px — and 16 px is where a logo most often actually appears:
the favicon, the notification icon, the list item.

The design target for Totto was:

> **Recognisable at 16 × 16 pixels, and still pleasant at 160 × 160.**

Everything that did not survive the 16 px test was removed. What remains is the
six elements above. There is nothing left to remove.

---

## Files

```
assets/
  v3-totto.svg   ← the mark (single continuous path + minimal parts)
  v2-otter.svg   ← rejected: too complex for small sizes
  v1-bear.svg    ← rejected: generic
docs/
  DESIGN.md      ← the full design rationale
```

All SVGs are dependency-free, use a `0 0 100 100` viewBox, and scale to any size
without loss.

---

## Usage

MIT licensed. Use it, remix it, ship it. Two requests, both about honesty rather
than law:

1. **Do not use Totto to imply endorsement.** If you fork this project, the otter
   should not appear to be speaking for Trustbase Lab.
2. **Do not put Totto next to a medical, financial, or legal claim.** It is a
   data company's mascot. It has no opinion about your health.

---

## License

MIT. See [LICENSE](LICENSE).

---

*Trustbase Lab · 2026*
