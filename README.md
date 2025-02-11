# ゲーム のタイトル
エアホッケー
## 実行環境の必要条件
* python >= 3.10
* pygame >= 2.1

## ゲームの概要
１つのPCで2つのパドルを動かし、２人で対戦ができるゲーム

## ゲームの実装
### 参考元のゲーム内容
* エアホッケーの当たり判定やゴール、ディスク、パドルなどの基本的な内容はせていさてていた
* 左側のゴールの当たり判定がない
* 片方のパドルの動きを止めるともう片方のパドルの動きも止まる
* パドルの斜め方向への移動ができない
* ゴールの後はディスクが中央から右下に向かって発射
* パドルが片方しか動くことができない(二つ同時に動かすことができない)
### 共通基本機能
* エアホッケーのフィールドに関するクラス
* エアホッケーのパドルに関するクラス
* エアホッケーのパックに関するクラス
### 元のゲームを調整
* 斜め方向への移動を可能にさせた
* パドルを２つ同時に動かせるようにした
* ゴールの判定の調整


### 担当追加機能
* パドルに当たるごとに速度変化(C0A22054)
パドルに当たるごとに速度が1.2倍になる
* 10点先取で勝利画面の表示(C0B22080)
「player1 win」のように2秒間表示させてゲームを終了
* パドルの大きさを変化させる(C0A22110)
5点差が付くと、負けているほうのパドルが同点になるまで大きくなる
* 障害物追加(C0B22048)
合計得点が5点を超えるとディスクを反射させる障害物追加
* お互いの得点差に合わせてゴールの大きさの変化(C0B22044)
2点差がつくと、勝っているほうのゴールの大きさが2倍。また、5点差が付くと6倍（ゴールに沿った壁全面）になる
* ゴールの後ディスクの発射方向を変化させる(C0A22030)
得点されたほうに向かってディスクが反射される
### ToDo
* ディスクの挙動が画面上部でおかしくなってしまうこと
* ディスクとパドルの当たり方がおかしい時があること
* ディスクが一定の角度でしか動かないこと
### メモ
* クラス内の変数は，すべて，「get_変数名」という名前のメソッドを介してアクセスするように設計してある
* すべてのクラスに関係する関数は，クラスの外で定義してある
参考文献
https://github.com/mkfeuhrer/Air-hockey