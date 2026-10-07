# Graffiti 予想（*Written on the Wall*）についての結果

[English](README.md)

木村心（Shin Kimura）、2026-10-07

結果は AI（Anthropic の Claude Opus 5.5 と OpenAI の GPT-6.1 Sol）の助けを借りて得た。

このリポジトリは、S. Fajtlowicz『Written on the Wall』（2004 年 7 月版）の予想についての結果の索引である。
『Written on the Wall』は、計算機プログラム Graffiti が出した予想の一覧である。
各結果の証明または反例と検証スクリプトは、下にリンクしたそれぞれのリポジトリにある。

## 一覧

| 予想 | 主張（略） | 結果 | リポジトリ |
|---|---|---|---|
| 322 | 三角形なし ⇒ Inverse Even ≤ 距離行列の固有値の range | **偽**：2048 頂点の反例 | [graffiti-322-counterexample](https://github.com/shiiiIIiIiiin/graffiti-322-counterexample) |
| 262 | −最小固有値 ≤ Even の最大値 | **真**（より強い形で） | [graffiti-262-proof](https://github.com/shiiiIIiIiiin/graffiti-262-proof) |
| 714 | −(0 以下の固有値の平均) ≤ すべての temperature の逆数の和 | **真** | [graffiti-714-proof](https://github.com/shiiiIIiIiiin/graffiti-714-proof) |
| 198 | 固有値の derivative の最小値 ≤ n / mean gravity | **真**（すべての連結グラフで） | [graffiti-short-proofs](https://github.com/shiiiIIiIiiin/graffiti-short-proofs) |
| 219 | 三角形なし ⇒ 重力行列の 2 番目に大きい固有値 ≤ 非辺の数 | **真** | 同上 |
| 252 | ラプラシアン固有値の derivative の最小値 ≤ 双対次数の逆数の和 | **真** | 同上 |
| 254 | ラプラシアン固有値の derivative の最小値 ≤ Odd の逆数の和 | **真** | 同上 |
| 712 | temperature の最小値 ≤ 0 以下の固有値の個数 | **真** | 同上 |
| 584 | 木 ⇒ ラプラシアンの最大固有値 ≤ 2 + 独立数 | 真。**X.-D. Zhang（2004）が証明済み**。短い証明を載せるのみで、新規性は主張しない | 同上 |

この作業の前、予想 198, 219, 252, 254, 262, 322, 712, 714 は、
M. Roucairol and T. Cazenave, *Refutation of Spectral Graph Theory Conjectures with Search Algorithms*
（[arXiv:2409.18626](https://arxiv.org/abs/2409.18626)、ECAI 2025）の表 1 で、
M. Aouchiche and P. Hansen, *A survey of automated conjectures in spectral graph theory*, Linear Algebra Appl. 432 (2010) 2293–2322
の状態に従って未解決とされていた。
文献と、私たちの知る 2026 年の追跡サイトを調べたが、どこか別の場所で既に解決されていた可能性は否定できない。

## 結果の概要

用語は T. L. Brewster, M. J. Dinneen, V. Faber, *A computational attack on the conjectures of Graffiti:
New counterexamples and proofs*, Discrete Math. 147 (1995) 35–55 の用語集に従う。
Even(v) は v 自身を含めて v から偶数の距離にある頂点の数、ベクトルの range は異なる成分の個数、
断りのない固有値は隣接行列 $`A`$ の固有値である。

- **322（反例）.** 2 元 Golay 符号 $`[23,12,7]`$ の剰余類グラフは、2048 頂点の三角形を含まないグラフである。
  どの頂点でも Even $`= 254`$ なので Inverse Even $`= 2048/254 = 1024/127 \approx 8.06`$ だが、
  距離行列の異なる固有値はちょうど 4 個（$`5842, 10, -14, -30`$）しかない。2 通りの独立な整数の厳密計算で確かめた。
- **262.** $`v`$ からちょうど距離 2 にある頂点の数を $`s_v`$ とすると、$`A + \mathrm{diag}(1 + s_v)`$ は半正定値である。
  したがって $`-\lambda_{\min}(A) \le 1 + \max_v s_v \le \max_v \mathrm{Even}(v)`$。
- **714.** 正の固有値の和を $`S`$、0 以下の固有値の個数を $`N`$、負の固有値の個数を $`q`$、平均次数を $`d`$ とすると
  $`S/N \le S/q \le (n-d)\sqrt{n/d} < n(n-d)/d \le \sum_v (n - d_v)/d_v`$。
  密なグラフは大きなクリークを持つので負の固有値が多く、負の固有空間への射影で $`S`$ を「辺のない場所」の数で抑える。
- **198, 219, 252, 254, 712.** 短い議論：固有値の間隔を、固有値の二乗和（198）や $`\lambda_{\max}(L) \le n`$（252, 254）と比べる。
  重力行列のフロベニウスノルムと Mantel の定理に、8 頂点以下の三角形を含まないグラフ 581 個の厳密な計算機検証を加える（219）。
  Turán 型のクリークの下限とコーシーのインターレース定理を使う（712）。
- **584.** Anderson–Morley の不等式 $`\lambda_{\max}(L) \le \max_{uv} (d_u + d_v)`$ と、三角形と長さ 4 の閉路がなければ
  辺の両端の近傍が大きさ $`d_u + d_v - 2`$ の独立集合になることを組み合わせる。

## 公開の記録

各リポジトリを最初に公開した日時（GitHub 上の作成日時、UTC）と、Internet Archive の保存記録。

| リポジトリ | 最初の公開 | 保存記録 |
|---|---|---|
| graffiti-322-counterexample | 2026-10-07 09:06 | [web.archive.org/web/20261007090623](https://web.archive.org/web/20261007090623/https://github.com/shiiiIIiIiiin/graffiti-322-counterexample) |
| graffiti-short-proofs | 2026-10-07 09:16 | [web.archive.org/web/20261007091807](https://web.archive.org/web/20261007091807/https://github.com/shiiiIIiIiiin/graffiti-short-proofs) |
| graffiti-714-proof | 2026-10-07 10:59 | [web.archive.org/web/20261007105927](https://web.archive.org/web/20261007105927/https://github.com/shiiiIIiIiiin/graffiti-714-proof) |
| graffiti-262-proof | 2026-10-07 11:36 | [web.archive.org/web/20261007113711](https://web.archive.org/web/20261007113711/https://github.com/shiiiIIiIiiin/graffiti-262-proof) |

予想 584 は、同じ日のあとから graffiti-short-proofs に追加した（リリース v1.1.0）。

## 出典

- S. Fajtlowicz, *Written on the Wall* (July 2004 version).
- T. L. Brewster, M. J. Dinneen, V. Faber, Discrete Math. 147 (1995) 35–55（用語集）.
- M. Aouchiche, P. Hansen, Linear Algebra Appl. 432 (2010) 2293–2322.
- M. Roucairol, T. Cazenave, arXiv:2409.18626 (ECAI 2025).
- X.-D. Zhang, *On the two conjectures of Graffiti*, Linear Algebra Appl. 385 (2004) 369–379.

## ライセンス

文章：CC BY 4.0。
