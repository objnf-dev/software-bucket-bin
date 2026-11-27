# software-bucket-bin

使用 [Pake CLI](https://github.com/tw93/pake) 将网页应用打包为 Windows x64 MSI 安装包。每个应用存放在独立目录中。

## 应用列表

| 应用 | 来源站点 | 安装包 |
| --- | --- | --- |
| Google 翻译 | [translate.google.com](https://translate.google.com/?sl=auto&tl=zh-CN&op=translate) | [pake-gtranslate.msi](pake-gtranslate/pake-gtranslate.msi) |
| 云·原神 | [ys.mihoyo.com](https://ys.mihoyo.com/cloud/#/) | [pake-genshincloud.msi](pake-genshincloud/pake-genshincloud.msi) |
| 云·崩坏：星穹铁道 | [sr.mihoyo.com](https://sr.mihoyo.com/cloud/#/) | [pake-hsrcloud.msi](pake-hsrcloud/pake-hsrcloud.msi) |

## 安装

下载对应应用的 MSI 文件，双击并按照安装向导完成安装。应用运行时需要访问对应的在线服务。

## 重新打包

安装 Pake CLI 及 [Tauri 构建依赖](https://tauri.app/start/prerequisites/)后，进入对应应用目录执行打包命令。例如在 `pake-gtranslate` 目录中执行：

```sh
pake 'https://translate.google.com/?sl=auto&tl=zh-CN&op=translate' --name pake-gtranslate
```

云·原神使用以下指定图标重新打包：

```sh
pake 'https://ys.mihoyo.com/cloud/#/' --name pake-genshincloud --icon 'https://webstatic.mihoyo.com/common/clgm-web-app/ys/img/logo_home_header.82e54fa5.png'
```

云·崩坏：星穹铁道使用以下指定图标重新打包：

```sh
pake 'https://sr.mihoyo.com/cloud/#/' --name pake-hsrcloud --icon 'https://webstatic.mihoyo.com/common/clgm-web-app/sr/img/logo_home_header.d98f2de5.png'
```

其他应用使用表格中的来源地址，并将 `--name` 设置为对应目录名。更多参数可运行 `pake --help` 查看。

## 许可证

本仓库内容采用 [The Unlicense](LICENSE)。第三方网页服务、图标及商标的权利归各自权利人所有。
