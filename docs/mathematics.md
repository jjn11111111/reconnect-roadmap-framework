# Mathematics

Formal sketches from the Grok session. Not peer-reviewed physics — **modular/harmonic coordinate notation** for the −0− model.

---

## Doubling cycle (digital root)

For `n = 0, 1, 2, …` let `v(n) = digital_root(2^n)`:

| n | 2ⁿ | digital root |
|---|-----|--------------|
| 0 | 1 | 1 |
| 1 | 2 | 2 |
| 2 | 4 | 4 |
| 3 | 8 | 8 |
| 4 | 16 | 7 |
| 5 | 32 | 5 |
| 6 | 64 | 1 |

Cycle: **1 → 2 → 4 → 8 → 7 → 5** (period 6).

---

## Seven-fractal (binding)

`1/7 = 0.142857…` — cyclic permutation **142857**.

For `k = 1…6`, the first digit of `k/7` indicates position in the binding personality set.

Binding path notation: **1 → 4 → 2 → 8 → 5 → 7**.

---

## Prime digital roots (first 48)

Reduction sequence (primes from 2):

```
2, 3, 5, 7, 2, 4, 8, 1, 5, 2, 4, 1, 5, 7, 2, 8, 5, 7, 4, 8, 1, 7, 2, 8,
7, 2, 4, 8, 1, 5, 1, 5, 2, 4, 5, 7, 4, 1, 5, 2, 8, 1, 2, 4, 8, 1, 4, 7
```

**Observation:** 3, 6, 9 never appear. Active set {1, 2, 4, 5, 7, 8} matches doubling cycle digits.

---

## Twelve-fold angular grid

- Full circle: 360°
- Sector width: 30° per position
- Position index: `k mod 12` for `k ∈ {0,…,11}`

### Chromatic assignment (C root)

| Pos | Pitch | Notes |
|-----|-------|-------|
| 0 | C | Zero reference |
| 3 | E♭ | Pump family |
| 6 | F♯ | Pump / inversion |
| 9 | A | Pump anchor ("unmoving mover") |

### Doubling path on 12-clock (semitone positions)

Gen 0: C(0) → D(2) → E(4) → G(7) → B(11) → F(5) → C(0) octave

---

## Coordinate signature (teleport / resonance sketch)

**Signature** `S = (R, θ, φ, P)`:

| Symbol | Definition |
|--------|------------|
| `R` | Radial octave level ∝ `2^n` |
| `θ` | Angular sector `(m mod 12) × 30°` |
| `φ` | Binding phase in 1-4-2-8-5-7 cycle, `φ ∈ {0,…,5}` |
| `P` | Pump lock, often anchored at 9 |

**Complex form (Grok):**

```
C = 2ⁿ × (cos(2π(m mod 12)/12), sin(2π(m mod 12)/12)) × e^(i·2π·φ/6) × 9^P
```

**Resonance condition** (source ≡ target at zero node):

- `R_s ≡ R_t` (mod octave equivalence)
- `θ_s ≡ θ_t` (mod 12)
- `φ_s ≡ φ_t` (mod 6)
- `P_s = P_t` (often 9)

When matched, model asserts toroidal identification of locations — **speculative** physically.

---

## Sator Square reductions (summary)

See [sator-square.md](./sator-square.md).

- Rows & columns: digital root → **1** (unity collapse)
- Main diagonal S-R-N-R-S: **1-9-5-9-1** → sum 25 → **7**
- Anti-diagonal R-P-N-P-R: **9-7-5-7-9** → **1**
- TENET center word: **252** (palindrome)

---

## Palindrome equation convention

Prefer:

```
1 × 1 = 1 × 1
```

over collapsed `= 1` to preserve bilateral mirror in notation.

---

## Implementation note (Phase 2)

Planned `tools/cycles.py` (or `.js`):

- `doubling_phase(n) -> 1|2|4|8|7|5`
- `binding_phase(k) -> 142857 index`
- `prime_reductions(limit) -> list`
- `signature_from_date(...) -> (R,θ,φ,P)` experimental
