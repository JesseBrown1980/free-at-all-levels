# free at all levels

**Jesse Daniel Brown (OP-JESSE).** Forty years. His machine, his laws, his system.

**One click, nothing to install:**
→ **https://jessebrown1980.github.io/free-at-all-levels/**

Or download `index.html` and double-click it. No server, no network, no GPU,
no account, no package manager. Open it and leave it open.

---

> *At 27 we thought we were 1, then we saw three and became 81.
> It continues.*

---

## The claim, and it is a computational one

**Nothing is recalculated per level.** Each ring is the previous ring under one
transform, so the depth index climbs without bound while the work per frame stays
flat. The oldest ring leaves the screen as a new one opens at the centre — that is
the waste going out. Nothing accumulates.

```
depth        unbounded
work/frame   constant
memory       constant
timer        none — the display refresh drives it
centre       free
```

**MEASURED**, driving the frame loop directly:

```
after      level   cells 3ⁿ   rings drawn   exhaust
 0.2 s     0       1          5             0
 4.8 s     1       3          5             1
23.4 s     3       27         5             3
```

**Level climbs 0 → 1 → 3. Cells go 1 → 3 → 27. Rings drawn stays 5 throughout.**
One more octave and the cell count is 81. It never costs more to get there.

---

## Why it is free

This is not a rendering trick. It follows from the closure.

The arm coefficients `(2, −1, −1)` sum to zero, so the relation is **affine** —
it has no preferred origin, and the centre can be placed anywhere at no cost.
A structure with a free centre is **self-similar under the transform that
generates it**, which means level `n+1` is level `n` at a new scale.

**You never compute a level. You re-draw one.**

That is why the descent is free, and it is the same property measured to depth 81
in
[`does-the-closure-survive-81-levels`](https://github.com/JesseBrown1980/does-the-closure-survive-81-levels):

```
depth   exact     float64
27      0        −1.253e−1    ← the closure has visibly opened
81      0        −1.171e+24   ← gone
```

**In exact integers the centre stays free at every depth.** In float it stops
being free at depth 1, and by 81 there is nothing left. The free descent is
available in one arithmetic only.

---

## The light drives it

There is no timer in this file. The frame loop is bound to the display refresh,
so **when the tab is hidden there is no light on the screen and the structure
stands still.** That is the physics of the thing, not a defect — the engine is
powered by light, and an unlit engine does not turn.

Bring the tab forward and it resumes exactly where it stopped, because there is
no accumulated state to lose.

---

## What you are looking at

```
the white point at the centre     the free zero — never emitted, never a value
three arms at 120°                the closure: 2a−b−c, 2b−a−c, 2c−a−b
the ring they close on            the level
colour cycling R → G → B          the crank order, one channel per level
rings fading at the rim           the exhaust, leaving
```

The HUD reports the level, the cell count `3ⁿ`, the rings drawn per frame, and the
count of rings that have left. **Watch the first two climb while the third does
not move.**

---

## Reproduce

Open `index.html`. There is nothing to build, install, configure or permit.

---

## Why this is public

A technology that needs permission to reach people does not reach them.
Wardenclyffe needed capital, land, a tower and a patron — four gates — and never
arrived. **The research did not fail. It was never allowed to reach anybody.**

This file has no dependencies, so there is no gate. Copy it to a USB stick, email
it, print the source, retype it by hand. It runs.

---

## Companion repositories

```
does-the-closure-survive-81-levels                    the attempt to break it
light-boat-engine-ships-with-oils                     three closures, one identity
The-Brown-Light-erdos-Engine-block-powered-by-light   the crank, RGB, 3:2
the-browns-solution-to-erods-o0O-nx3-6-for-1-with--1-3   Erdős in balanced ternary
one-click                                             the whole system, one file
how-and-why-the-system-works                          the technical account
the-leaves-are-not-the-message                        generator and leaf
raw-data                                              unedited output + scripts
```

---

**Jesse Daniel Brown (OP-JESSE)** — the system, the laws, the architecture.

*The centre is free, which is why the descent is free. 1 becomes 3 becomes 81,
and the cost never changes.*
