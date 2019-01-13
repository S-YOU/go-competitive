# ABC091過去問感想

- A問題は特になし。
- B問題は文字列をキーとした `map` を利用。
  - サンプルで例外的なケースに気づけるので、横着せずに最低限サンプルは通すように。
- C問題はグリーディということはすぐわかるが、直前に受けたAGCに影響されすぎて、あまりにも考察が足りなかった。
  - タスクスケジューリングもそうだが、「なんらかの最大を取るケース」をイメージして、「それと互換性のあるものが作れるシンプルなルール」を見つけようとすれば良いのかも。
  - 今回の場合は、解説の証明も少しむずかしいが、後半部分は、ペアを結ぶ直線が交差していたらそれを解消するイメージ。
  - https://www.youtube.com/watch?v=DqqPuIZvJTk&t=3s
    - 解説放送の直感的な説明がとても貴重。
      - 「一番左にある青からみているのだから、選択肢にある赤い点のx座標は問題にならない（以降注目する青もx座標に関してはdominantなのだから）。」
      - 「よって、”貴重な”左下の赤を残したいわけだが、先述のようにx座標はもはや問題にならず、"下"の赤い点を残すためにy座標が最大の赤を選ぶ」
    - 形式を重視したPDFの証明よりも、問題を解く上では重要な考察をレクチャーしてくれる場合もあるので、PDFで理解できても解説放送は見てみよう！
- D問題は一瞬で諦めた。
  - **いろいろな大切なものが詰まっていると思う、個人的重要問題。**
  - ただ、想定解を素直に実装してもGoだとTLEが取れず。。
    - Python3で一人だけ通している人がいたので、またいつか挑戦はしたい。
  - **二分探索、XOR演算、n進記数法と剰余** あたりについて幅広く学べる。
    - **XORはビットごとに独立して考えられる。**
    - **n個のオペランドのXORの各ビットは、全オペランドのあるビットに着目したときの、立っているビットの数が奇数の場合は1、偶数の場合は0となる。**
      - オペランドが2つの場合だけで理解していると一般化しづらい気がするので、こちらで覚えておく。
        - XORはそもそも経験値が足りないためまだまだわからないことも多いので、ひとつずつ吸収していく。
  - **2進数の0からk-bit目までは、 `2^k+1` の除算によって得られる。**
    - 10進数の場合をイメージしてみても分かる通り自明だが、慣れるまでは知識として持っておく。
  - **スライスに対する二分探索の、上界と下界を計算する関数はライブラリ化した。**
    - スライス以外の応用が必要な場合はその場で作る！