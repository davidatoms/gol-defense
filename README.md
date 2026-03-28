# Conway's Game of Life — Defense Grid

---

## Thank You

This project would not exist without a chain of curiosity and generosity from people who took the time to share ideas publicly.

Thank you to the mathematicians and researchers at **Cambridge University** whose work on cellular automata, number theory, and computational complexity laid the foundation this project sits on.

Thank you to **Lex Fridman** for interviewing both **Terence Tao** and **Demis Hassabis** on his podcast. Those conversations — on the nature of mathematics, intelligence, and the structure of reality — are what brought Conway's Game of Life into focus for me as something worth building with, not just reading about.

John Conway gave us a universe in a grid. Terence Tao reminded us that mathematics is a living thing. Demis Hassabis showed us what happens when you take pattern and structure seriously enough to build minds from it.

This project is an attempt to sit at that intersection.

---

## What This Is

A Conway's Game of Life simulation built as a spatial reasoning and diagramming tool. The grid is not just a toy — it is a substrate for exploring how mathematical structure, boundary conditions, and emergent computation interact.

Every layer added to this project corresponds to a real mathematical or physical idea:

- **The simulation** — a discrete dynamical system, Turing complete, built from four rules
- **The coordinate grid** — an Excel-style reference frame for navigating and naming positions
- **The sequence markers** — prime numbers, twin primes, Fibonacci, perfect squares, and tens radiating outward from center as spatial frequency markers
- **The dividers** — V, X, Y, Z — four half-axes that partition the grid into quadrants with controllable boundary conditions
- **The boxes** — user-drawn regions of interest with per-side Dirichlet boundary conditions (open, wall, null)
- **The hardness system** — a unified open/wall/null state model applied consistently across dividers, sequence lines, and drawn boxes

---

## The Mathematics

The neighbor-counting step is a discrete 2D convolution with a 3×3 uniform kernel. The birth/survival rules are a non-linear activation function applied to the convolution output. The full step is mathematically:

```
grid_next = f(grid, grid * K)
```

Where `K` is the Moore neighborhood kernel and `f` is the Conway transition function.

The sequence lines are drawn from the integers outward:

| Sequence | Growth | Mathematical basis |
|---|---|---|
| Primes | Sub-linear (density ~ 1/ln n) | Sieve of Eratosthenes |
| Twin Primes | Thins faster than primes | Twin prime conjecture (open) |
| Fibonacci | Exponential (ratio → φ) | F(n) = F(n-1) + F(n-2) |
| Perfect Squares | Quadratic | n², spacing grows as 2n+1 |
| Tens | Linear | Uniform baseline |

The hardness states are Dirichlet boundary conditions: wall fixes a cell to 1, null fixes it to 0, open leaves it free.

---

## Structure

```
index.html   — Conway's Game of Life simulation with all layers and tools
grid.html    — Standalone Excel-style spreadsheet with formula support
pages.html   — Field notes — feature documentation with GIF placeholders
BUGS.md      — Known issues
README.md    — This file
```

---

## Branches

| Branch | Contents |
|---|---|
| `main` | Initial commit |
| `feature/rulers` | Canvas rulers on all four edges |
| `feature/dividers` | V/X/Y/Z center dividers |
| `feature/observation-layers` | Age, heatmap, neighbors, population |
| `feature/sequence-markers` | Prime, twin prime, Fibonacci, square markers |
| `feature/shape-layers` | Full-grid lines at sequence positions |
| `feature/pump` | Pump button with strength slider |
| `feature/patterns` | Pattern insert menu |
| `box-layers-hardened` | Concentric sequence boxes |
| `draw-box` | User-drawn boxes with per-side hardness, sequence hardness panel |

---

## Repository

[github.com/davidatoms/gol-defense](https://github.com/davidatoms/gol-defense)
