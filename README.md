# Cisco Packet Tracer 简体中文笔记
## 通用Switch基本配置
*以下命令通常在全局配置模式


## 超基本命令
```
enable               !特权模式,通常简写 en
configure            !全局配置模式，通常简写 conf
end                  !返回到特权模式
show running-config  !查看修改配置，通常简写 sh r
ip routing           !在三层交换机启用的路由功能
````
<br>
<br>



## 设备名称
配置Switch,Router设备名称
```
Host <User>           !配置设备名称,Switch和Router通用,可简写成 Ho Switch1
```
<br>
<br>



## 配置密码
*以下命令均在全局配置模式
配置Switch,Router设备密码,密码有分明文
```
enable password 123  !明文密码 123,可简写成 en pas 123
enable secret 123    !密文密码 123,可简写成 "en sec 123"
```
<br>
<br>



## Telnet 远程登命令
###  Switch二层交换机
Switch二层交换机和三层交换机配置相同
和Router唯一不同的就是 "Login" 命令 和 "login local" 命令，后者适用于路由器
```
line vty 0 4          !0 4指0到4五个接口
pass 456              !配置密码
login                 !启用登录模式
```
<br>
<br>



### 三层交换机
```
line vty 0 4           !0 4指0到4五个接口
pass 456               !配置密码
login local            !启用登录模式
```
<br>
<br>



## 二层交换机的 Consle
二层交换机的 Consle 口 密码配置
```
line con 0           !指进入0口
pas 123
login
```
<br>
<br>



## 配置接口描述
```
int f0/1             !进入Fa0/1端口,通常简写 f0/1
des example          !配置描述内容为example
```
<br>
<br>



## VLAN 配置
*以下命令均在全局配置模式
```
vlan 2               !创建 VLAN 2 命令不区分大小写
na v2                !修改VLAN名字为 v2 ,区分大小写. 取消修改命令可以用 no na v2
```
<br>
<br>



## 添加到端口,添加单一接口
要先进入端口, 用 int 命令,之后在配置
*以下命令可能简写
```
sw ac vlan 2         !把该端口添加到 VLAN 2
```
<br>
<br>



## 添加到端口,添加多个接口
多接口添加到VLAN, 连续的的多接口可以用 "-" 符号,例如 fa0/2到fa0/4 端口用 int f0/2-4 ,单端口用 "," 英文逗号符号
```
in ra f0/2-4,f0/7,f0/8
sw ac vlan 2
```
<br>
<br>



## Trunk模式
启用Trunk模式
```
in f0/2              !可以使用多接口
sw m t               !命令 SW M T, 启用Trunk模式
```
<br>
<br>



## Trunk接入允许通过的VLAN
```
sw t a vlan 2
```
<br>
<br>
