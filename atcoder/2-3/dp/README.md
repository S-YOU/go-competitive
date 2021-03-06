# Dynamic Programming

全探索を効率的に行う。

## ナップサック問題

- メモを利用しない素直な深さ優先探索をベースに考えると理解しやすい
    - 重さの制限の情報が必要なのは、メモの有無とは別
- メモの初期化をしっかりすること
    - `N+1` まで初期化しないと、再帰の終了条件が正しく呼ばれず、正しい答えが出ない
- 再帰関数の場合、基本手順を染み込ませる
    1. メモの参照
    2. 終了条件のチェック
    3. 探索
    4. 1-3を踏まえてメモに記録の上、値を返して関数を終了する
- 個人的に漸化式で `i` 番目の品物を選ぶときに `j - w[i]` とするときになにか引っかかるものがあるが、
**`i` 番目の品物を選ぶという条件のもと、重さの制約 `j` のとき得ることができる価値の最大値を考えると、 `dp[i][j-w[i]]` を使わなければならない** と訳すことができる。

- 漸化式で解く場合、`dp` 配列の定義を踏み外さないことを意識しつつ、最後に出力する添字に注意

## 制限から推測

- `100 * 10000` 程度のメモで済むならDPを要検討
    - Goで最大 `10 * 1024 * 1024` の3重ループでも2秒制限の問題を1.5秒くらいで通せた
- 純粋なビット全探索では `n=10` 程度が標準（？）

## パターン集

### 部分和問題

- `dp[i][j](dp [][]bool): dp[i][j]: i番目以降の問題集合から任意個整数を選んだとき、和j点を取れるかどうか`
    - 直接 `dp[0][goal]` を出力すれば目標の和が取れるかどうかがわかる
    - `dp[0][j]` ですべての和について調べれば、パターン数も調べることができる

### bool値を求めるDP

- **無駄があることが多いため、同じ計算量でもっと多くのことを知ることができる。**
    - `dp[i+1][j]` にbool値以外の情報をもたせることを検討する（`false` を表す数値として `-1` を使うのは定石（？））
- `プログラミングコンテストチャレンジブック第二版 P.62～P.63` の解説における `dp[i+1][j-a[i]]` を考えるところは最初？だったが、
**漸化式であることを考えると `j - k*a[i]` を考える必要はない（途中で考えていることになる）** と考えれば良い
    - `dp[i+1][j] = dp[i+1][j-a[i]] - 1` のように、DPテーブルの上からだけでなく左から平行に伝搬するパターンもあるという点に注意したい

### 確率の問題（TDPCのD問題）

- **配るDP** で足していくとうまくいくことが多い（らしい）

### ゲーム系の問題（TDPCのB問題）

- 最善手を考える場合などは、ゲームの終了から考えるとよいらしい

### 桁DP（TDPCのE問題）

- 漸化式を思いつくのは簡単だが、それを運用して答えを求めるところが本番かもしれない
    - TDPCのE問題は剰余算に関して実装的にもいろいろと網羅できるので、忘れた頃に解き直すのにちょうどよい問題と思われる

---

## 漸化式を作るときの意識

- 各項のそれ以前の項がすでに求まっていると仮定すること
    - 数学的帰納法のようなイメージで
    - 添字が複数あるからややこしいが、動かす添字と固定する添え字を意識しながら考える
- 初項はどう考えられるか？というところからスタートするのも良い
    - 2変数ならば `dp[0][0]` から考えてみる、そこから次が計算できるかを考える
- ときにヒントになりうるキーワード
    - 部分問題
    - 状態、遷移
