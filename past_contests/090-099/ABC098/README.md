# ABC098過去問感想

- A問題はちゃんとMax関数を使って省エネしよう。
- B問題はBにしては少し実装が面倒な部類。
  - `ans` の初期値を雑に設定してしまったためにコーナーケースで1つWAしてしまったので、初期値設定は低難度の問題でも慎重に。
- C問題は累積和なのはパット見でわかるのに、実装に時間がかかりすぎてしまった。
  - 変にメモリ節約をしようとして最初に時間を無駄にしてしまったので、ときはじめは割と贅沢なコードを書いても良い。
    - まずそうだったら最後にリファクタリングすればよい、ベースのコードがあれば雑になら簡単に治せる。
- D問題はXORなので頑張りたかったが、ギブアップ。
  - しゃくとり法なる手法の問題らしい。
