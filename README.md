# JCT AI Studio 安装包

这里发布 **JCT AI Studio（君城 AI 开发平台）** 的安装包和每个版本的更新说明。本仓库只放安装包，不含源码。

JCT AI Studio 是装在你自己服务器上的 AI 开发平台：每位员工一台独立的云端电脑，AI 在里面写代码、运行、看报错、开浏览器自测，跑通后提交到 Git。

- 产品介绍：<https://www.97network.com/ai-studio/>
- 体验版与部署教程：<https://www.97network.com/ai-studio/trial/>
- 使用教程：<https://www.97network.com/ai-studio/docs/>

## 下载

到 [Releases](https://github.com/lnzz123/jct-ai-studio-releases/releases) 下载，[最新版本在这里](https://github.com/lnzz123/jct-ai-studio-releases/releases/latest)。每个版本有两个文件：

| 文件 | 说明 |
| --- | --- |
| `jct-ai-studio-<版本>.tar.gz` | 安装包，里面有网关镜像、门户前端、编排配置和安装、升级脚本 |
| `jct-ai-studio-<版本>.tar.gz.sha256` | 安装包的 SHA-256 校验值 |

体验版和正式版是同一个安装包。不填授权码就是体验版：免费 30 天，最多 5 个账号，功能完整。到期后填入授权码转为正式版，数据保留，不用重装。

下载后可以核对文件是否完整：

```bash
sha256sum -c jct-ai-studio-<版本>.tar.gz.sha256
```

## 安装

服务器要求：Linux x86_64（建议 Ubuntu 22.04 或 24.04）、Docker Engine 24 以上、内存 8 GB 起、`/srv` 下至少 30 GB 可用空间、一个 HTTPS 域名。

```bash
tar xzf jct-ai-studio-<版本>.tar.gz && cd jct-ai-studio-<版本>
sudo ./install.sh --url https://studio.example.com
```

把 `studio.example.com` 换成你的域名。安装完成后脚本会打印一条初始化链接，打开它创建第一个管理员并添加模型。完整步骤见[体验版与部署教程](https://www.97network.com/ai-studio/trial/)。

## 升级

已经装好的系统有两种升级方式：

- **在线升级**：管理后台的“系统设置 → 版本与授权”里点“检查更新”，有新版本时点“升级”。
- **用安装包升级**：下载新版本，解压后执行 `sudo ./upgrade.sh`。

两种方式都会先备份数据库和配置，升级失败自动回滚。

## 授权与联系

JCT AI Studio 是贵州君城网络科技有限公司的商业软件，安装和使用需遵守授权协议。安装包里包含的开源组件按各自的许可证授权，清单见安装包内的 `THIRD_PARTY_NOTICES.md`。

购买授权、预约演示或部署遇到问题，请通过[官网](https://www.97network.com/about#contact)联系我们。

版权所有 © 2026 贵州君城网络科技有限公司。保留所有权利。
