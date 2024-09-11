# 部品の選定
以下に主要な部品の選定について記載する。

## カメラ：Realsense D435
[参考リンク](https://www.amazon.co.jp/gp/product/B07BLS5477/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)
※ IMUが搭載された**Realsense d435i**が存在するが、d435に比べて電力消費量が大きく、Jetson Xavier NXがd435iに接続された状態でbootしないバグが発生するため、d435を使用することを推奨する。

## モータ：Emax Eco 1404 6000kv
[参考リンク](https://ja.aliexpress.com/item/1005001622396096.html?gatewayAdapt=4itemAdapt)
シリーズ1404には、6000kv, 4800kv, 3700kvの3種類が存在するが、kvが高いほど電力消費量が大きくなるため、より低いkvのモータを検討することを推奨する。

## ESC：15A 4in1 ESC
ESCはモータのkv, バッテリーの電圧などに応じて選定する必要がある。本PJでは下記のESCを使用しているが、BLHeli_Sがデフォルトでフラッシュされ再フラッシュできなくなっているため、やや不便である。できればシリアルポート接続できBLHeli_32が利用できるESCが望ましい。

[参考リンク](https://www.amazon.co.jp/RC%E3%83%89%E3%83%AD%E3%83%BC%E3%83%B3%E9%9B%BB%E5%AD%90%E3%82%B9%E3%83%94%E3%83%BC%E3%83%89%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%BC-1%E3%83%9F%E3%83%8B%E9%9B%BB%E5%AD%90%E3%82%B9%E3%83%94%E3%83%BC%E3%83%89%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%BC%EF%BC%88%E3%82%B1%E3%83%BC%E3%83%96%E3%83%AB-%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B5%E3%83%AA%E3%83%BC-%EF%BC%89%E3%83%89%E3%83%AD%E3%83%BC%E3%83%B3RC%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B5%E3%83%AA%E3%83%BC-%E7%94%A8ESC/dp/B09WTR1V5M)

## プロペラ：HQ Prop 3.5 inch
[参考リンク](https://ja.aliexpress.com/item/1005005448644389.html?spm=a2g0o.order_list.order_list_main.5.1832585ajwZ0TT&gatewayAdapt=glo2jpn)

## フレーム：Happymodel frame kit
メインフレーム以外はすべて3Dプリントで作成するが、モータフレームのみ強度が求められるので既成品を使用する。メインフレーム以外のフレームデータは[Google Drive]()からダウンロードできる。

[参考リンク](https://ja.aliexpress.com/item/1005006170048907.html?spm=a2g0o.order_list.order_list_main.5.6eb0585azLl2rg&gatewayAdapt=glo2jpn)

## フライトコントローラ：Holybro Kakute H7 Mini
2024/9時点で最も小さく、外部位置推定を受け付けるメモリのあるフライトコントローラ。結構繊細なので複数買っておくことを推奨する。(筆者はすでに3つ破壊した)

[参考リンク](https://holybro.com/products/kakute-h7-mini)

## バッテリー：2S/3S Lipo >= 2000mAh
ハード選定は2Sで飛ばすことを想定している。ただし2Sで容量の大きいLipoバッテリーは希少なため、3Sを使用することを検討しても良い。

[参考リンク](https://ja.aliexpress.com/item/1005007182572003.html?spm=a2g0o.order_list.order_list_main.35.4cdd585auwXlP0&gatewayAdapt=glo2jpn)

## RCトランスミッター：Jumper T-Pro V2
トランスミッターはチューニング及びデバッグ用であるため最小限のものを選定している。

[参考リンク](https://wda-jp.com/shop/products/detail/1957)

## RCレシーバー：フタバR2000SBM

[参考リンク](https://wda-jp.com/shop/products/detail/363)

## WiFi子機：TP-Link Archer T3U Nano

[参考リンク](https://www.amazon.co.jp/TP-Link-%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC%E4%BF%9D%E8%A8%BC3%E5%B9%B4-Archer-T3U-Nano/dp/B0B6HTRL4P/ref=asc_df_B0B6HTRL4P/?tag=jpgo-22&linkCode=df0&hvadid=622912241506&hvpos=&hvnetw=g&hvrand=396206296343700935&hvpone=&hvptwo=&hvqmt=&hvdev=m&hvdvcmdl=&hvlocint=&hvlocphy=1009343&hvtargid=pla-1835926581116&mcid=75816e6d02453c62a50f94763d8bef5f&th=1)

## メインプロセッサ：Jetson Xavier NX 8gb
機能、価格ともにドローンの中心部品であるので、慎重に選定することを推奨する。
2024/9時点ではJetsonシリーズの選定対象はXavier NX 8gb, 16gb, Orin NX 8gb, 16gbの4つである([比較表](https://connecttech.com/orin-xavier-comparison/))。
本PJではXavier NX 8gbを使用しているが、性能面ではOrinシリーズに大きく劣るため、Orin NX 8gbあたりを検討すると良いと思われる。しかし、Xavier NXの開発ボードキット以外にはmicroSDスロットが存在せず外部NVMeに依存する仕様であるため、注意する必要がある。また、開発ボードキットのキャリアボードはLinuxカーネルのフラッシュには有用であるが、実装には下記のキャリアボードを使用するため、ボードは省いて生産モデルを購入しても良い。しかしその場合は前述したとおり外部NVMeを用意する必要があることに留意する。

[参考リンク](https://www.amazon.com/NVIDIA-Jetson-Xavier-Developer-812674024318/dp/B086874Q5R)

## キャリアボード：冬虫電子 NCB00
Jetson Xavier NXのキャリアボードは複数の種類が存在するが、本PJでは冬虫電子のNCB00を使用している。Orinシリーズを仕様する場合は、Orin NX用のキャリアボードであるOCB00を使用する必要がある。

[参考リンク](https://ja.aliexpress.com/item/1005004075300322.html?gatewayAdapt=glo2jpn)