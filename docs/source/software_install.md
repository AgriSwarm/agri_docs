# Install Software

## Xavier NXのフラッシュ

Jetson Xavier NXのフラッシュには2通りある
1. pc(host)でmicroSDをフラッシュ(balenaEtcher / [Jetpack5.0.2](https://developer.nvidia.com/embedded/jetpack-sdk-502)) ⇒ xavierに刺してboot
2. pc(host)に[Jetpack SDK Manager](https://developer.nvidia.com/sdk-manager)を入れる ⇒ xavierをリカバリーモードで起動しusb経由でflash

基本2が安全だがmicroSDによってはうまくできないこともあるのでそのときは使い分ける。

## Setup スクリプトの実行

各モジュールの動作に伴う種々のセットアップを行うためのスクリプトを実行する。