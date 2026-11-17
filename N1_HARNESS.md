# N1 harness branch (on top of upstream DLO-Lab 4af0562)

This branch adds two commits to upstream DLO-Lab commit 4af0562 ("Fix random seed issue").
They were used for the CBF safety-filter benchmark of the thesis-dlo project.

| commit | what it does |
|---|---|
| fd5d5da | `wiring_post`: passes `K=1e5, use_inextensible=False` to `ROD.Base`, so the stretching energy is computed (upstream leaves both unset, i.e. `K=0`, inextensible). |
| 2eb5342 | Harness patches, all gated by environment variables. **With every variable unset the code behaves as upstream 4af0562.** It also replaces fd5d5da's two literal lines with the plant switch below, so fd5d5da's rope is used only when that switch asks for it. |

Switches added by 2eb5342 (all optional):

| variable | effect |
|---|---|
| `DLOLAB_WIRING_PLANT` | `paper` (default) = upstream rope kwargs of `wiring_post`; any other value = the extensible rope of fd5d5da (`K=1e5, use_inextensible=False`). Each run prints a `[plant] ...` line. Affects `wiring_post` only. |
| `DLOLAB_GRASP_IDX` | grasp-vertex switch |
| `DLOLAB_TEST_DUMP_VERTS` | dumps rope vertices during test episodes |
| `DLOLAB_CMAES_SAVE_POP` | saves the CMA-ES population |
| `DLOLAB_GD_EARLY_STOP` | early stop for the gradient-descent baseline |
| `DLOLAB_GS_SEED` | overrides the Genesis seed |

The thesis runs used `DLOLAB_WIRING_PLANT=paper`, i.e. the upstream rope.
