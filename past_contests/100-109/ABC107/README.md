# ABC107過去問感想

- A問題は特になし。
- B問題は素直にシミュレーションしようとしたが、忠実すぎると2次元配列の行・列のdeleteが必要になり混乱する。
  - 言語依存で難易度が変わってしまうし、行はともかく、列のdeleteが大変すぎるので別の方法をもっと早く取るべきだった。
  - **残すべき行・列のスライスIDXを残しておき、最後にその情報をもとに1行1行文字列を作成し、都度出力していけば良い。**
  - 数少ない、「Bの中では復習する価値が高い問題」ではあると思う。
- C問題は一見難しいが、選んだスライス区間に対して要する時間を計算する式がわかると、シンプルな部分スライスの全探索になる。
  - 気づくのがちょっと遅すぎる。
  - PDFでは本質的には同じことをやっているが、自分のコードよりも場合分けが圧縮されておりスマート。
    - 今回に関しては「解ければよいのだ」で終わりにしておく。
- D問題は700点だったのでもっと強くなってからまた。。
