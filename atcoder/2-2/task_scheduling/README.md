# 区間スケジューリング問題

- 終端でソートしてgreedy algorithmで最適解が得られる。
    - `ある最適解が存在する場合、選んだ中で最も早く終る仕事を、他にもっと早く終る仕事があれば置き換えても良い`
    ということと `最も早く終る仕事と、それを選んだことにより選べなくなった仕事を除いた仕事集合を考え、再帰的に問題を考える`
    という2つの視点から考えると理解できる。
- 一見区間スケジューリング問題に見えないものでも適用範囲は広いので注意。
