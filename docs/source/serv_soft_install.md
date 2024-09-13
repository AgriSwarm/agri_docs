# サーバー機のセットアップ

## 前提環境

ドローン本体とは別に、以下環境を用意したPCが必要です。

| Item | Description |
|:----:|:-----------:|
| OS | Ubuntu 20.04 |
| ROS | Noetic |

## Mission Planner

### Mono install
Windowsネイティブなアプリなので、Monoで仮想実行する必要がある。
```bash
sudo apt install ca-certificates gnupg
sudo gpg --homedir /tmp --no-default-keyring --keyring /usr/share/keyrings/mono-official-archive-keyring.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb [signed-by=/usr/share/keyrings/mono-official-archive-keyring.gpg] https://download.mono-project.com/repo/ubuntu stable-focal main" | sudo tee /etc/apt/sources.list.d/mono-official-stable.list
sudo apt update

sudo apt install mono-devel
```
### download
```bash
cd $HOME/Downloads
wget https://firmware.ardupilot.org/Tools/MissionPlanner/MissionPlanner-latest.zip
unzip MissionPlanner-latest.zip
cd MissionPlanner
```
### run
```bash
mono MissionPlanner.exe
```

## Rviz

### install
```bash
sudo apt install ros-noetic-rviz
cd $HOME/catkin_ws/src
git clone git@github.com:AgriSwarm/agri_resources.git
cd $HOME/catkin_ws
catkin build agri_resources
catkin source
```
### run
```bash
roslaunch agri_resources rviz.launch
```