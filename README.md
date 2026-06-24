# Nezha v0 CN - 哪吒监控面板

修改自 [nezhahq/scripts](https://github.com/nezhahq/scripts)，支持 Linux/FreeBSD/OpenBSD/NetBSD 平台，并内置 GitHub 镜像加速源。

## 功能特性

- 支持多平台：Linux、FreeBSD、OpenBSD、NetBSD
- 支持 ARM64/ARM 架构
- 内置 GitHub 镜像加速（自动测速选择最优节点）
- 支持 Docker / 独立安装
- Agent 版本固定：v0.20.5
- Dashboard 版本：v0.20.13

## 快速开始

### 交互式安装

```bash
curl -L https://raw.githubusercontent.com/daoke123/nezha-v0-cn/main/nezha-v0-cn.sh -o nezha-v0-cn.sh
chmod +x nezha-v0-cn.sh
sudo ./nezha-v0-cn.sh
```

### 加速安装命令

使用以下命令自动使用 GitHub 镜像加速：

```bash
# 加速源 1
curl -L https://gh-proxy.com/https://raw.githubusercontent.com/daoke123/nezha-v0-cn/main/nezha-v0-cn.sh -o nezha-v0-cn.sh && chmod +x nezha-v0-cn.sh && sudo ./nezha-v0-cn.sh

# 加速源 2
curl -L https://cdn.gh-proxy.com/https://raw.githubusercontent.com/daoke123/nezha-v0-cn/main/nezha-v0-cn.sh -o nezha-v0-cn.sh && chmod +x nezha-v0-cn.sh && sudo ./nezha-v0-cn.sh

# 加速源 3
curl -L https://gh-proxy.org/https://raw.githubusercontent.com/daoke123/nezha-v0-cn/main/nezha-v0-cn.sh -o nezha-v0-cn.sh && chmod +x nezha-v0-cn.sh && sudo ./nezha-v0-cn.sh
```

### 非交互式安装

#### 安装面板（Docker 模式）

```bash
sudo ./nezha-v0-cn.sh install_dashboard
```

#### 安装面板（独立模式）

```bash
sudo ./nezha-v0-cn.sh install_dashboard
```

#### 安装 Agent

```bash
sudo ./nezha-v0-cn.sh install_agent <域名> <端口> <密钥>
```

示例：
```bash
sudo ./nezha-v0-cn.sh install_agent nezha.example.com 5555 your_client_secret
```

## 使用帮助

```bash
./nezha-v0-cn.sh                        # 显示管理菜单
./nezha-v0-cn.sh install_dashboard      # 安装面板端
./nezha-v0-cn.sh modify_dashboard_config # 修改面板配置
./nezha-v0-cn.sh start_dashboard        # 启动面板
./nezha-v0-cn.sh stop_dashboard         # 停止面板
./nezha-v0-cn.sh restart_and_update     # 重启并更新面板
./nezha-v0-cn.sh show_dashboard_log     # 查看面板日志
./nezha-v0-cn.sh uninstall_dashboard    # 卸载管理面板

./nezha-v0-cn.sh install_agent          # 安装监控 Agent
./nezha-v0-cn.sh modify_agent_config   # 修改 Agent 配置
./nezha-v0-cn.sh show_agent_log        # 查看 Agent 日志
./nezha-v0-cn.sh uninstall_agent       # 卸载 Agent
./nezha-v0-cn.sh restart_agent         # 重启 Agent
```

## 平台支持

| 平台 | 包管理器 | 服务管理 |
|------|----------|----------|
| Debian/Ubuntu | apt | systemctl |
| CentOS/RHEL | yum | systemctl |
| Arch Linux | pacman | systemd |
| Alpine | apk | rc-service |
| FreeBSD | pkg | service |
| OpenBSD | pkg | rcctl |
| NetBSD | pkgin | service |

## 架构支持

- x86_64 (amd64)
- i386 (386)
- aarch64 (arm64)
- arm (arm)
- s390x
- riscv64

## GitHub 镜像加速

脚本内置自动测速功能，会依次尝试以下镜像源：

1. `https://gh-proxy.com`
2. `https://cdn.gh-proxy.com`
3. `https://gh-proxy.org`

如果都不可用，将回退到官方 GitHub 源。

## 鸣谢

- 原作者：[naiba](https://github.com/naiba/nezha)
- [nezhahq](https://github.com/nezhahq)
- [Xun-X](https://github.com/Xun-X/Nezha-v0)

## License

AGPL-3.0 License
