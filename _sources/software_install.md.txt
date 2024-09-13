# Software System

ドローンの通信システムは以下のように構成されています。
![comm_system](_static/comm_system.png)

ドローンの通信には大きく分けて2つのモードがあります。

**1. シングルエージェントモード**

単機での通信を行うモードでは、ルーターを介さずにJetsonをアクセスポイントかつROSマスターとして動作させ、laptopをWiFiでJetsonに接続します。この場合システムがインターネットを利用できなくなることに注意してください。
![comm_system](_static/comm_system_single.png)

**2. マルチエージェントモード(未実装)**

複数機での通信を行うモードでは、Jetsonをクライアントとしてルーターに接続し、laptopもルーターに接続します。この場合システムがインターネットを利用できるため、ROSパッケージのダウンロードやアップデートが可能です。

![comm_system](_static/comm_system_multi.png)