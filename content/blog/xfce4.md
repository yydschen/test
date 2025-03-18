---
title: "Debian 12上安装XFCE4桌面"
date: 2023-12-20
category: 折腾
tags: [linux,应用,折腾]
---

1. 更新系统软件包：
```cmd
sudo apt update
sudo apt upgrade
```

2. 安装XFCE4桌面及相关组件：
```cmd
sudo apt install xfce4 xfce4-goodies
sudo apt install thunar xfce4-terminal
```

3. 安装xrdp：
```cmd
sudo apt install xrdp
```

4. 启动xrdp服务：
```cmd
sudo systemctl start xrdp
```

5. 设置xrdp服务开机自启动：
```cmd
sudo systemctl enable xrdp
```

6. 检查xrdp服务状态：
```cmd
sudo systemctl status xrdp
```

7. 如果防火墙已启用，请确保允许RDP流量通过：
```cmd
sudo ufw allow 3389
```
8. 配置xrdp端口，默认端口号为3389，此处配置假设为666
```cmd
sudo sed -i 's/port=3389/port=666/g' /etc/xrdp/xrdp.ini

```
9. 重新启动系统：
```cmd
sudo reboot
```

安装完毕后，您可以使用RDP客户端连接到您的Debian 12系统，并使用XFCE4桌面环境。