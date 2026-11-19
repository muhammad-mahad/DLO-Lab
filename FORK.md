# This fork: what is here and why

`main` = upstream [UMass-Embodied-AGI/DLO-Lab](https://github.com/UMass-Embodied-AGI/DLO-Lab) `main` (all upstream commits) plus this one file. Our own changes live on the branches below. Cite commits by hash, never by branch name (a branch head can move).

| branch | base (upstream) | commits of ours | what it is | use |
|---|---|---|---|---|
| `n1/harness-on-4af0562` | 4af0562 | fd5d5da, **2eb5342**, 593f4ec | `wiring_post` extensible-rope lines (fd5d5da); harness patches, all gated by environment variables, unset = upstream 4af0562 (2eb5342); notes (593f4ec, see `N1_HARNESS.md`) | **run code of record** of the thesis-dlo benchmark: commit 2eb5342 |
| `fix/wiring-post-stretching-stiffness` | c5026a9 | **dd1aa6e** | `wiring_post`: `K=1e5, use_inextensible=False` (same patch as fd5d5da on the older base) | cited in our errata; reading copy only, not a run tree after 16 Oct 2026 |
| `fix/wrapping-stretch-denominator-4af` | 4af0562 | 150dc93 | `wrapping`: the stretching-failure check divides by the control-point geodesic, not the total rope length | fix proposed for upstream; never a run tree |
| `archive/4090-dlo_lab-1d0fd59` | c5026a9 | 1d0fd59 | same tree as dd1aa6e (identical files, different commit); the 4090 copy that Genesis is imported from | archive only, so the hash can be found |
| `contrib/install-verify-analysis` | c5026a9 | e3fb72d, ea76db8 | install guide, task verification script, unknotting failure analysis | upstream PR #1 (closed); history |
| `n1/consolidated-on-4af0562` | 4af0562 | fd5d5da, **2eb5342**, 5531fb7 (150dc93 ported behind `DLOLAB_STRETCH_DENOM=geodesic`), **93f9491** (W6 SDF grid padding v2 behind `DLOLAB_SDF_PAD_M`), **64436df** (ea76db8's INSTALL.md, verify_tasks.py, analyze_unknotting_failure.py and a .gitignore line; standalone, nothing imports them) | the ONE branch we consolidate onto, started at 2eb5342 itself (19 Nov 2026). Both new flags default OFF. Identity with 2eb5342 when the flags are off rests on a code trace (line 525, 19 Nov: no changed body line runs with the flags off; the 7 gate lines run), not on bit-identical outputs. Flag ON = a new plant variant, never a plant of record. 1d0fd59 has nothing left to port (its committed tree equals dd1aa6e = fd5d5da; its 4 uncommitted files are an obsolete seed variant superseded by upstream 4af0562 and 2eb5342). **Consolidation complete; old branches kept** (20 Nov 2026) | **2eb5342 stays the code of record for every run of record** |

Removed 18 Nov 2026: `fix/gathering-genesis-init` (upstream PR #3, closed; no commits left) and `fix/wrapping-stretch-denominator` (duplicate of 150dc93 on the old base, dc66b41).
