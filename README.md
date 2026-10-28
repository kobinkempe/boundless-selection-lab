# bound.less Selection Feedback Lab

**A UX prototyping lab for showing what is selected when a drawing object is too small, too thin or too large for an ordinary selection box.**

In [bound.less](https://github.com/kobinkempe/bound.less-kk), an object can be smaller than a pixel or larger than the whole viewport. Its box may be off screen, or a thick highlight may hide the detail being selected. I wanted to compare ways of keeping selection understandable across those extremes.

AI helped prototype alternative indicators on shared scenes, so I could judge their coverage, visual weight, motion and clarity. Try marching ants, a clamped frame, corner ticks, object shimmer and tint with edge marks on the same difficult shapes. These are design studies used to inform product decisions.

## Public demo

[Open the live lab](https://kobinkempe.pages.dev/boundless-selection-lab/) · [See project details](https://kobinkempe.pages.dev/projects/boundless-selection-lab/)

![Selection feedback experiment](docs/screenshots/desktop.jpg)

## Run

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Open http://127.0.0.1:8000. Start with the scene overview, then compare marching ants, a clamped frame, corner ticks, object shimmer, and tint/edge marks. The stripped-down ant page isolates geometry from the rest of the interface.

## Design question

A conventional bounding box loses meaning when all its corners are outside the viewport. In bound.less, the old dashed selection box also caused a real stall at deep zoom, because the app redrew a box far larger than the screen on every frame. A thick highlight can obscure a tiny mark, while a faint outline can disappear against the drawing. The experiments apply alternative indicators to shared scenes so the tradeoffs can be compared directly.

The pages explore feedback presence, coverage, visual weight, motion and scale. They are concept prototypes, not a shipped component library or an accessibility certification. After trying them in the app, I chose marching ants along the object’s own edge. When an object runs off screen, the ants follow the screen edge instead, with a small arrow pointing to where the object continues. The shimmer looked promising in the studies, but I didn’t like it in use, so I dropped it.

## Portfolio contribution

This complements the bound.less renderer with product judgment: translate a difficult geometry constraint into understandable interaction alternatives, then make those alternatives easy to inspect. AI assisted the prototyping process; no model runs inside the demo.

The portfolio copy adds a landing page and removes optional network font imports so the experiments work locally. Existing scene geometry remains intact. Static references and JavaScript syntax are checked, and the live page is inspected in Chrome.

## Source

Extracted from [bound.less](https://github.com/kobinkempe/bound.less-kk). `PROVENANCE.json` maps the included experiments to their upstream paths and records the standalone snapshot hashes and adaptations.
