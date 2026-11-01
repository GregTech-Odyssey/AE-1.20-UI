# AE-1.20-UI · GTO 适配分支

[GregTech Odyssey（GTO）](https://gtodyssey.com) 整合包专用的 [AE-1.20-UI](https://github.com/GregTech-Odyssey/AE-1.20-UI) 材质包分支。

本分支以 [`master-1.20.1`](https://github.com/GregTech-Odyssey/AE-1.20-UI/tree/master-1.20.1) 为底包，针对 **Minecraft 1.20.1 + GregTech Odyssey 0.6.0（dev25）** 的模组环境补齐界面，提供亮色 `LightMode` 与暗色 `DarkMode` 两个版本。

## 下载与安装

1. 在 Releases 页下载 `AE-Light-UI-*.zip` 或 `AE-Dark-UI-*.zip`；没有现成产物时也可以克隆本分支自行打包（见下一节）。
2. 把 zip 放进实例的 `minecraft/resourcepacks/` 目录。
3. 游戏内「选项 → 资源包」启用它，并移到列表最上方（否则会被其他资源包覆盖）。
4. 按 `F3 + T` 重载资源。

> 直接把 `LightMode/` 或 `DarkMode/` 文件夹放进 `resourcepacks/` 也可以，效果与 zip 相同。

## 本地打包

需要 `bash` 与 `zip`：

```bash
git clone -b gto https://github.com/GregTech-Odyssey/AE-1.20-UI.git
cd AE-1.20-UI/scripts
bash pack.sh
# 产物：AE-1.20-UI/pack/LightMode.zip、AE-1.20-UI/pack/DarkMode.zip
```

## 与 master-1.20.1 的差异

1. **不携带任何 `assets/*/lang`**
   界面文案完全交给模组与整合包，避免资源包里的旧翻译覆盖 GTO 的汉化。
2. **ME 二合一终端完整主题**
   面板外框、槽位格、玩家背包面板（`me2in1_player_inv.png`）、缩放角、折叠按钮、样板发送行等全部换成包内配色（含无线二合一终端）。
3. **合成存储器动画面补齐 `.png.mcmeta`**
   1k~256k 的 `*_storage_light` 是 8 帧动画条带，资源包覆盖时必须同时提供 mcmeta，否则会被压成静态贴图、显示错纹。
4. **可读性修正**
   拖拽齿轮常态可见、文本框焦点色、暗色下 GT 机器底板/进度条、uipro 配色方案、任务书与科技树画布。
5. **GTO 专属内容**
   GTOCore 加速卡 (II)~(V)、分级 ME 接口、AE 附属模组（AdvancedAE、ExtendedAE、MEGA Cells、neoecoae 等）的界面适配，以及二合一终端的专属面板。

完整改动清单见两包内的 `CREDITS.txt`。

## 目录结构

```text
AE-1.20-UI/
├── DarkMode/          # 暗色主题资源包
├── LightMode/         # 亮色主题资源包
├── scripts/pack.sh    # 本地打包脚本（输出到 pack/）
├── docs/              # 上游多模组文档（英文 / 简体中文）
├── .github/           # Issue 模板与自动发布工作流
├── VERSION            # 当前分支版本号
└── LICENSE            # GNU LGPLv3
```

## 注意事项

- 仅修改 UI 贴图与界面布局，不改变模组逻辑。
- 仅适用于 Minecraft 1.20.x。
- 与其他 AE 风格 UI 资源包互斥，请只启用其中一个。
- 本分支不含语言文件；如果界面文案异常，请检查模组或整合包自带的语言文件，而不是资源包。

## 致谢

- 原作：[LeeQianXi](https://github.com/LeeQianXi) 的 AE-1.20-UI Multi-module。
- GTO 适配：GregTech Odyssey 团队。
- 许可：GNU LGPLv3，全文见 [LICENSE](LICENSE)；修改版同样以 LGPLv3 发布。

---

## English

This branch is the GregTech Odyssey–specific adaptation of AE-1.20-UI for **Minecraft 1.20.1 / GTO 0.6.0-dev25**. It provides the light (`LightMode`) and dark (`DarkMode`) packs.

Differences from `master-1.20.1`:

- No `assets/*/lang` files, so modpack translations are never overridden.
- Complete ME 2-in-1 terminal theming, including the new draggable player-inventory panel.
- Animated storage-cell textures ship their `.png.mcmeta`.
- Contrast fixes for draggable panel handles, text fields, GT machine UIs, the quest book and the tech tree.
- GTO-exclusive content: speed cards II–V, tiered ME interfaces and AE add-on UIs.

Install: download a release or run `scripts/pack.sh`, put the zip into `resourcepacks`, enable it and move it to the top, then press `F3 + T`. Licensed under LGPLv3. Original pack by LeeQianXi.
