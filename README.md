# Wuji Hand Upgrader

Wuji Hand Upgrader - 用于机器人灵巧手升级的桌面应用

## 系统要求

- **操作系统**: Linux (Ubuntu 20.04+)
- **架构**: x86_64 (AMD64)

## 安装方式

### Debian 包 (.deb)（推荐）

Debian 包提供系统级安装，适合需要集成到系统菜单的用户。安装后会自动配置串口权限和用户组。

#### 下载
下载最新对应版本的 .deb 文件：
- GitHub Releases：https://github.com/wuji-technology/wujihand-upgrader-hmi/releases

#### 安装步骤

1. **使用 apt 安装应用程序**
   注意：将 <downloaded-latest-package-name> 替换为实际下载的软件包名称。
   ```bash
   sudo apt install ./<downloaded-latest-package-name>.deb
   # 如遇依赖问题可执行
   sudo apt-get install -f
   ```

3. **运行应用程序**
   
   在桌面端点击“WUJI”APP图标运行

#### 权限配置
安装完成后，系统会自动：
- 开放串口设备访问权限
- 将当前用户添加到相应的用户组
- 配置必要的硬件访问权限

#### 时序要求
固件升级时，需要满足以下时序：
1. 灵巧手处于断电状态，先打开wujihand-upgrader应用程序
2. 灵巧手先通过USB连接到PC，然后再给灵巧手通电
3. wujihand-upgrader会自动连接到灵巧手引导程序
4. 正常连接后可进行固件升级操作

**注意**：若连接后提示当前不处于引导程序，需要重新给灵巧手上电

#### 卸载
```bash
sudo apt remove wujihand-upgrader
```

**注意**: 首次运行可能需要较长时间来解压和初始化应用程序。请耐心等待。



