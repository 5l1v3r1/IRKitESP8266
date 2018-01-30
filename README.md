IRKitESP8266
=====

IRKit Clone on ESP8266

## これは何

Toshiyuki Kawashima氏の[ESP8266IRKit](https://github.com/toskaw/ESP8266IRKit) をベースに、以下の2点の追加・改変を行ったものです。
* ボタンを追加、長押しで初期化(電源ON時にも有効)
* 動作状態をLED(WS2812B)で表示

## 基板データ

IRKitESP8266.{brd,sch}がEagleデータです。適当な方法で製造してください。

※LED電流制限抵抗としてR4とR11の2つがありますが、どちらか一方のみの実装でよいです。流れる電流からして、R11のほうがオススメです（13Ωと書いてありますが、10Ω前後のものでよいはず）。ただこのあたりは要調整で、SwitchScienceのESP-IRではもっと小さな抵抗を使っているようです。10Ωか4.7Ωの0603サイズ（インチ：ミリだと1608）を、R4とR11の両方に実装するくらいでいいかもです（試していないのでLED破損の恐れがありますので要注意）。

なおオリジナルIRKitの基板と、穴の位置やコネクタの位置を基本的にあわせてあるので、オリジナルの筐体を流用できます。ただしオリジナルの赤外線LEDは2個なので、その筐体に合わせる場合は、LEDはD3とD4のみとりつけ、電流制限抵抗R4/R11もそれにあわせて調節してください。なおステータス表示LEDは基板上に上向きに実装されるため、オリジナル筐体にはあいません。またタクトスイッチの位置・種類がオリジナルと異なります。ご了承ください。

※初期化用タクトスイッチをオリジナル筐体にあうように追加し、プログラム用ショートピンの位置を少しずらし、ESP8266のアンテナ周囲のベタGNDを設計ガイドラインにあわせてあけたv1.1を追加しました(C5の位置が変更になっています)。ただし実際の製造・検証はしてませんのでご了承ください。


## ソースコード

上記のToshiyuki Kawashima氏の「作り方（ソースからコンパイルする方法）」の通りに進めます。


## 使い方

基本的に純正IRKitと同じです。スマホのIRKitアプリで初期設定を行ってください。初期パスワードは"0000000000"です。


## 参考にしたもの

* [minlRum](https://github.com/9SQ/minIRum)

* [IRKit](http://getirkit.com/)

* [ESP8266IRKit](https://github.com/toskaw/ESP8266IRKit)

## 直近のToDo
* LED点滅を、一応実装した（1秒周期）が、IR受信時の点滅を本家にあわせたい。
* 基板の外形・部品位置を、オリジナル筐体にあうように、以下の修正をしたい。
** uUSBコネクタの位置
** 初期化タクトスイッチ
** 角を丸める

## Author

Junichi Akita (@akita11, akita@ifdl.jp)
