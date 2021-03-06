# todo for tdd

- [x] データ構造を定義する
    - [x] 隣接行列でエッジと重みを決める
        - [x] 隣接行列は、メソッドからノード間の重みを設定できる
        - [x] 隣接行列は、メソッドを介して重みを取得できる
        - [x] 隣接行列は、初期状態ではエッジなしとする
            - [x] エッジなしを-1で表現する
        - [x] 重みの取得とセットで引数チェックを行い、例外処理を行う
        
- [x] wikipediaのダイクストラの説明の初期データを入力する

- [x] 優先度付きキューを用いないダイクストラのアルゴリズムを実装する
    - [x] 必要なデータ構造の初期化
        - [x] スタート地点から各地点への暫定の最短距離を記憶する **スライス** を定義（スタート地点のみ0、それ以外は∞）
        - [x] 各地点のそのコストを得るために経由する直前の点を記憶する **スライス**　を定義（すべてなし）
        - [x] 探索候補の点集合を格納するキュー（ **スライス** ）を定義（すべての点を追加）
    - [x] 探索キューから暫定最短距離が最小の頂点を取得するメソッドを定義
    - [x] 出力は、ゴールまでの最短路とそのコストのペアとする

---

# ダイクストラの要点

- コストがminの点をキューから取得した段階で、その点へのスタートからの最短路が決定する
    - 「常にコストが低い点を選び続ける（キューから取り出しチェックする対象とする）」という方針であるため、スタートから経由できる他のいずれの点をえらんでも、よりコストを小さくすることはできない、と主張できる。
- 確定した各点の最短路は、直前のノード番号を辿っていくことで取得できる。
- 計算量はノード数の2乗（最悪、各点のチェック時にほかの点に伸びるエッジをすべて調べる必要があるため）
    - ヒープなどの優先度キューが利用できると線形対数まで落とせる

## 復習時のメモ

- 負の経路が存在する場合は、最短路が正しく求まるとは限らない
    - 理由: ↑で書いた「コストがminの点をキューから取得する」をサポートする方針の前提に逆らっているため。
        - まだ見ることができていないエッジが負のコストを持つ場合、コストがminの点をあえて選ばないほうが、俯瞰してみるとより小さいコストとなる可能性がある。
        - 極端な例として、-infなエッジの存在を仮定すれば良い。
