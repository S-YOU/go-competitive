# Union-Find（蘇州号データ構造）

https://www.slideshare.net/chokudai/union-find-49066733/1

グループ分けを管理し、**「まとめる」と「判定」の2つのクエリに対応する。**

**経路圧縮**: 根を調べる際に、親を直接グループの根に張り替える。
**ランク**: 木の高さを保持し、低い方を高い方につなげる。

## 計算量

経路圧縮のみでおおよそ `O(log(n))` 。

## 注意点

Union-Find木はグループを併合することはできても **分割することはできない。**
