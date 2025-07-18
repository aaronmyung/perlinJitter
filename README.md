# perlinJitter

A lightweight, self-contained C++ library for generating smooth 2D jitter using classic 1D Perlin noise. Ideal for simulating natural motion paths, cursor drift, animation jitter, and procedural offsetting in real-time systems.

> Header-only. Zero dependencies. Fast. Easy to use.

Required: C++11 or later

---

## 📦 Features

* Classic 1D Perlin noise implementation
* Randomised 2D jitter with configurable amplitude and frequency
* Runtime reseeding for dynamic behaviours
* Minimal dependencies
* Single-header integration

---

## 🔧 Use Case Examples

* Natural input simulation (e.g. mouse jitter or drift)
* Procedural animation offsetting
* Temporal noise for dynamic effects
* Education and experimentation with Perlin noise

---

## 📄 Header Overview

```cpp
#include "perlin_jitter.h"

PerlinJitter jitter;
Vec2 offset = jitter.get_offset(time_in_seconds);
```

You can call `.reset()` to re-randomise the internal parameters.

---

## ✨ Output Example

Calling `get_offset(t)` returns a `Vec2` where both `x` and `y` are smoothly-varying noise values based on time.

```cpp
Vec2 PerlinJitter::get_offset(double t) const;
```

Internally, both axes are driven by independent 1D Perlin noise streams with randomised amplitude, frequency, and seed offsets.

---

## 🧠 Behind the Scenes

This is a simplified Perlin implementation using:

* A permutation table (`p`)
* Smoothstep-like `fade` function
* Basic linear interpolation (`lerp`)
* 1D gradient hashing (`grad`)
* Seed offsets for temporal uniqueness

---

## 📚 License

MIT License.

---