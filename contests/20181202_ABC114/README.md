# ABC114感想

- A, B問題については特になし。
- C問題で朽ち果てた。
  - つまるところ順列の問題と考えて良さそう。
  - 考え方はあっていたが正しい実装を選択できなかった。
  - 模範解答の再帰関数を主軸に学び直し、途中で力尽きてしまった3進数変換の解法もやり直したい。
  - 次回以降のための反省
    - A,Bにも言えることだが、時間を気にするあまり、方針が固まりきっていないのにふわふわしたままコードを書くと、デバッグで無限に時間を持っていかれる。
      - 特に、C,Dに関してはちゃんと脳内で正当性を担保しないとまずACできない。
        - 10重のｋｓforループは戒めとして残しておく。
- D問題は約数の個数に関する問題（時間を残してたどり着ければ解けたような気がしなくもないが、どこかで詰まってる確率が高そう。。）
  - 動的計画法を使いたくなる要素が盛りだくさんだが、もっと素直に考えればよい。
  - **基本: 約数の個数は、素因数分解したときのそれぞれの指数+1の積で求まる。**
  - 最後の数え上げも自分にとってはそれほど自明ではなかったが、その方法は重要だと思われる。
    - 最初に考えたように、2個以上4個未満。。とか考えてしまうと、多分答えにたどり着けなくなる。
