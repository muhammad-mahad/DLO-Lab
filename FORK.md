# This fork: what is here and why

`main` = upstream [UMass-Embodied-AGI/DLO-Lab](https://github.com/UMass-Embodied-AGI/DLO-Lab) `main` (all upstream commits) plus this one file. Our own changes live on the branches below. Cite commits by hash, never by branch name (a branch head can move).

| branch | base (upstream) | commits of ours | what it is | use |
|---|---|---|---|---|
| `n1/harness-on-4af0562` | 4af0562 | fd5d5da, **2eb5342**, 593f4ec | `wiring_post` extensible-rope lines (fd5d5da); harness patches, all gated by environment variables, unset = upstream 4af0562 (2eb5342); notes (593f4ec, see `N1_HARNESS.md`) | **run code of record** of the thesis-dlo benchmark: commit 2eb5342 |
| `fix/wiring-post-stretching-stiffness` | c5026a9 | **dd1aa6e** | `wiring_post`: `K=1e5, use_inextensible=False` (same patch as fd5d5da on the older base) | cited in our errata; reading copy only, not a run tree after 16 Oct 2026 |
| `fix/wrapping-stretch-denominator-4af` | 4af0562 | 150dc93 | `wrapping`: the stretching-failure check divides by the control-point geodesic, not the total rope length | fix proposed for upstream; never a run tree |
| `archive/4090-dlo_lab-1d0fd59` | c5026a9 | 1d0fd59 | same tree as dd1aa6e (identical files, different commit); the 4090 copy that Genesis is imported from | archive only, so the hash can be found |
| `contrib/install-verify-analysis` | c5026a9 | e3fb72d, ea76db8 | install guide, task verification script, unknotting failure analysis | upstream PR #1 (closed); history |
| `n1/consolidated-on-4af0562` | 4af0562 | fd5d5da, **2eb5342** (so far; ports follow: 150dc93, the W6 SDF fix, the contrib files; each env-gated, default OFF) | the ONE branch we are consolidating onto, started at 2eb5342 itself (19 Nov 2026) | work in progress; 2eb5342 stays the code of record for every run of record |

Removed 18 Nov 2026: `fix/gathering-genesis-init` (upstream PR #3, closed; no commits left) and `fix/wrapping-stretch-denominator` (duplicate of 150dc93 on the old base, dc66b41).
