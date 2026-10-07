# Results on Graffiti conjectures (*Written on the Wall*)

[日本語](README.ja.md)

Shin Kimura (木村心), October 2026

The results were obtained with the help of AI (Claude Opus 5.5 by Anthropic and GPT-6.1 Sol by OpenAI).

This repository is an index of results on conjectures from S. Fajtlowicz, *Written on the Wall* (July 2004 version),
the list of conjectures produced by the computer program Graffiti. Each result, with its proof or counterexample and
verification scripts, is in its own repository linked below.

## Summary

| conjecture | statement (abbreviated) | result | repository |
|---|---|---|---|
| 322 | triangle-free ⇒ Inverse Even ≤ range of eigenvalues of Distance | **false**: counterexample on 2048 vertices | [graffiti-322-counterexample](https://github.com/shiiiIIiIiiin/graffiti-322-counterexample) |
| 262 | −smallest eigenvalue ≤ maximum of Even | **true** (in a stronger form) | [graffiti-262-proof](https://github.com/shiiiIIiIiiin/graffiti-262-proof) |
| 714 | −mean of nonpositive eigenvalues ≤ sum of reciprocals of all temperatures | **true** | [graffiti-714-proof](https://github.com/shiiiIIiIiiin/graffiti-714-proof) |
| 198 | minimum of derivative of eigenvalues ≤ n / mean gravity | **true** (for every connected graph) | [graffiti-short-proofs](https://github.com/shiiiIIiIiiin/graffiti-short-proofs) |
| 219 | triangle-free ⇒ 2nd largest eigenvalue of Gravity ≤ number of nonedges | **true** | same |
| 252 | minimum of derivative of eigenvalues of Laplacian ≤ sum of reciprocals of the dual degree | **true** | same |
| 254 | minimum of derivative of eigenvalues of Laplacian ≤ sum of reciprocals of Odd | **true** | same |
| 712 | minimum temperature ≤ number of nonpositive eigenvalues | **true** | same |
| 584 | tree ⇒ maximum eigenvalue of Laplacian ≤ 2 + independence | true; **already proved by X.-D. Zhang (2004)** — short proof only, no novelty claimed | same |

Before this work, conjectures 198, 219, 252, 254, 262, 322, 712 and 714 were listed as open in
M. Roucairol and T. Cazenave, *Refutation of Spectral Graph Theory Conjectures with Search Algorithms*
([arXiv:2409.18626](https://arxiv.org/abs/2409.18626), ECAI 2025), Table 1, following the status in
M. Aouchiche and P. Hansen, *A survey of automated conjectures in spectral graph theory*, Linear Algebra Appl. 432 (2010) 2293–2322.
We searched the literature and the 2026 trackers we knew of, but cannot exclude that some of these were settled elsewhere.

## The results in brief

Terms are as in the glossary of T. L. Brewster, M. J. Dinneen, V. Faber, *A computational attack on the conjectures of Graffiti:
New counterexamples and proofs*, Discrete Math. 147 (1995) 35–55: Even(v) counts the vertices at even distance from v
including v itself, the range of a vector is its number of distinct components, and eigenvalues without qualification are
those of the adjacency matrix $`A`$.

- **322 (counterexample).** The coset graph of the binary Golay code $`[23,12,7]`$ is triangle-free with 2048 vertices.
  Every vertex has Even $`= 254`$, so Inverse Even $`= 2048/254 = 1024/127 \approx 8.06`$, while the distance matrix has
  exactly 4 distinct eigenvalues ($`5842, 10, -14, -30`$). Verified by exact integer computations in two independent ways.
- **262.** $`A + \mathrm{diag}(1 + s_v)`$ is positive semidefinite, where $`s_v`$ is the number of vertices at distance exactly 2
  from $`v`$; hence $`-\lambda_{\min}(A) \le 1 + \max_v s_v \le \max_v \mathrm{Even}(v)`$.
- **714.** With $`S`$ the sum of the positive eigenvalues, $`N`$ the number of nonpositive eigenvalues, $`q`$ the number of
  negative ones and $`d`$ the average degree: $`S/N \le S/q \le (n-d)\sqrt{n/d} < n(n-d)/d \le \sum_v (n - d_v)/d_v`$.
  A dense graph has a large clique, hence many negative eigenvalues, and the projection onto the negative eigenspace
  bounds $`S`$ by the number of non-edges.
- **198, 219, 252, 254, 712.** Short arguments: spacing of eigenvalues against their sum of squares (198) or against
  $`\lambda_{\max}(L) \le n`$ (252, 254),
  the Frobenius norm of the gravity matrix with Mantel's theorem plus an exact computer check of the 581 triangle-free graphs
  on at most 8 vertices (219), and Turán-type clique bounds with Cauchy interlacing (712).
- **584.** Anderson–Morley's bound $`\lambda_{\max}(L) \le \max_{uv} (d_u + d_v)`$ together with the fact that, without
  triangles and 4-cycles, the neighbourhoods of an edge give an independent set of size $`d_u + d_v - 2`$.

## Publication record

First publication of each repository (time of creation on GitHub, UTC) and snapshots on the Internet Archive.

| repository | first published | snapshot |
|---|---|---|
| graffiti-322-counterexample | 2026-10-07 09:06 | [web.archive.org/web/20261007090623](https://web.archive.org/web/20261007090623/https://github.com/shiiiIIiIiiin/graffiti-322-counterexample) |
| graffiti-short-proofs | 2026-10-07 09:16 | [web.archive.org/web/20261007091807](https://web.archive.org/web/20261007091807/https://github.com/shiiiIIiIiiin/graffiti-short-proofs) |
| graffiti-714-proof | 2026-10-07 10:59 | [web.archive.org/web/20261007105927](https://web.archive.org/web/20261007105927/https://github.com/shiiiIIiIiiin/graffiti-714-proof) |
| graffiti-262-proof | 2026-10-07 11:36 | [web.archive.org/web/20261007113711](https://web.archive.org/web/20261007113711/https://github.com/shiiiIIiIiiin/graffiti-262-proof) |

Conjecture 584 was added to graffiti-short-proofs later the same day (release v1.1.0).

## Sources

- S. Fajtlowicz, *Written on the Wall* (July 2004 version).
- T. L. Brewster, M. J. Dinneen, V. Faber, Discrete Math. 147 (1995) 35–55 (glossary of terms).
- M. Aouchiche, P. Hansen, Linear Algebra Appl. 432 (2010) 2293–2322.
- M. Roucairol, T. Cazenave, arXiv:2409.18626 (ECAI 2025).
- X.-D. Zhang, *On the two conjectures of Graffiti*, Linear Algebra Appl. 385 (2004) 369–379.

## License

Text: CC BY 4.0.
