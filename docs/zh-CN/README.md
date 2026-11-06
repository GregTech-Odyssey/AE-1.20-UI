# AE-1.20-UI 多模组适配

适配 Minecraft 1.20.x（`pack_format` 15）的 Applied Energistics 风格 UI 材质包，为多模组提供统一的 AE 风格界面，同时优化 UI 的文本与贴图显示效果。

本仓库基于原作者 LeeQianXi 的 [AE-Light-UI Multi-module](https://www.curseforge.com/minecraft/texture-packs/ae-light-ui-multi-module) 维护，按 LGPLv3 许可发布。

我们为大量模组添加了 AE 风格的 UI，分亮色和暗色 2 个版本，例如：
- **应用能源 2**（Applied Energistics 2）及其扩展
- **精妙存储**（Sophisticated Storage/Core）
- **格雷科技**（GregTech Modern）与 **GTOCore**
- **农夫乐事**（Farmer's Delight）
- **无尽贪婪**（Avaritia）
- ……完整清单见下文「适配的模组」。

## 版本
- 支持 Minecraft 1.20.x（`pack_format` 15）
- 亮色（`LightMode`）/ 暗色（`DarkMode`）双版本
- 版本号见仓库根目录的 `VERSION` 文件；发布包由 CI 读取该文件打 tag 生成

## 核心特性
1. **双风格 UI 资源**
   提供`LightMode`（亮色主题）和`DarkMode`（暗色主题）两种 UI 资源包，满足不同玩家的视觉偏好。
2. **多模组适配**
   为多个热门 Minecraft 模组添加 AE 风格的界面适配，覆盖生存、存储、科技类模组，让不同模组的界面保持视觉统一。
3. **UI 细节优化**
   包含 UI 文本修正与贴图修正，修复部分模组 UI 的显示瑕疵，提升界面的美观度与可读性。
4. **整合包专属适配**
   针对[GregTech-Odyssey（GTO）](https://gtodyssey.com)整合包进行专门适配，完美兼容该整合包的模组环境。
5. **轻量适配**
   仅修改 UI 相关资源，不影响模组的核心功能逻辑，与模组的原版功能完全兼容。

## 安装与使用
1. **获取资源包**
   可以直接从仓库的 Releases 页面下载 `AE-Light-UI-<版本>.zip` / `AE-Dark-UI-<版本>.zip`，或克隆仓库本地自行打包：
    ```bash
    git clone https://github.com/GregTech-Odyssey/AE-1.20-UI.git
    cd ./AE-1.20-UI
    git switch gto            # GTO 适配版；基础包使用 master-1.20.1
    cd scripts && bash pack.sh  # 产物为仓库根目录 pack/ 下的 LightMode.zip 与 DarkMode.zip
    ```
    > `pack.sh` 依赖 `zip` 命令（Linux / macOS 自带；Windows 上可用 7-Zip 等工具手动压缩 `LightMode/` 与 `DarkMode/` 目录）。
2. **安装步骤**
    - 将下载或打包出的 zip（或 `LightMode/`、`DarkMode/` 文件夹）放入 Minecraft 的`resourcepacks`目录中
    - 启动 Minecraft，在「选项 → 资源包」界面中，将本材质包移动到资源包列表的最上方
    - 应用资源包后，即可体验 AE 风格的 UI 界面

## 适配的模组
当前覆盖 70 余个模组命名空间（`LightMode/assets/` 75 个、`DarkMode/assets/` 76 个，均含 `minecraft`），主要包括：

- **AE2 及其扩展**：Applied Energistics 2、Advanced AE、ExtendedAE、Expanded AE、ExtendedAE Plus、MEGA Cells、AE2WTLib、AE2 Things、AE2 Additions、AE2 Network Analyser、AppFlux、AppMek、AppliedE、ME Requester 等
- **存储**：Sophisticated Storage / Sophisticated Core / Sophisticated Backpacks、Functional Storage
- **科技与魔法**：GregTech Modern、GTOCore、Botania、MythicBotany、ArsEng（Ars Énergistique）
- **工具与界面**：JEI、EMI、FTB Quests、Building Gadgets 2、LaserIO、Pipez、Modular Routers、Chisel Reborn、Apotheosis、Curios、Crafting Tweaks、Travel Anchors、Touhou Little Maid 等

完整清单可直接查看 `LightMode/assets/` 与 `DarkMode/assets/` 下的命名空间目录。

## 目录结构说明
```Plain
AE-1.20-UI/
├── docs/              # 仓库文档（中文 / 英文）
├── LightMode/         # 亮色主题UI资源，包含该主题下的所有界面贴图与配置
├── DarkMode/          # 暗色主题UI资源，包含该主题下的所有界面贴图与配置
├── Tool/              # 贴图制作使用的像素替换工具
├── scripts/           # 材质包构建相关脚本文件（pack.sh）
├── .github/           # CI：PR 合并后按 VERSION 打 tag 出包，另含 CLA 与 PR 正文检查
├── VERSION            # 当前版本号
├── CONTRIBUTING.md    # 贡献指南
├── LICENSE            # 许可证（LGPLv3）
└── README.md          # 项目快速说明文档
```

## 适配整合包
- **GregTech-Odyssey（GTO）**：专门针对该整合包进行了适配，可直接在该整合包中使用本材质包，获得统一的 AE 风格界面体验。
  - `gto` 分支的产物已合并 GTO 叠加包，启用这一个包即可，无需再单独加载基础包。
  - 基础包（`master-1.20.1` 分支）不含 GTO 专属界面，GTO 整合包请使用 `gto` 分支的产物。

## 注意事项
1. 本材质包需要放在资源包列表的最上方，否则其 UI 效果可能会被其他资源包覆盖
2. 本材质包与其他 AE 风格的 UI 材质包不兼容，使用时请禁用其他同类型的 UI 材质包
3. 仅支持 Minecraft 1.20.x（`pack_format` 15），不兼容其他版本的 Minecraft 客户端

## 贡献
如果你想要参与本项目的开发，为更多模组适配 AE 风格 UI，或反馈 UI 的显示问题，欢迎通过以下方式参与：
1. 在仓库的 Issues 页面提交问题反馈或功能建议,或是提议后续适配的mod
2. Fork 仓库后提交 Pull Request，贡献你的适配内容
3. 提交 PR 前请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)；本仓库的 PR 需要签署 CLA，并通过 PR 正文检查
