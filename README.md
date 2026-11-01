# AE-1.20-UI · GTO 适配分支

[GregTech Odyssey（GTO）](https://gtodyssey.com) 整合包专用的 [AE-1.20-UI](https://github.com/GregTech-Odyssey/AE-1.20-UI) 材质包分支。

本分支以 [`master-1.20.1`](https://github.com/GregTech-Odyssey/AE-1.20-UI/tree/master-1.20.1) 为底包，针对 **Minecraft 1.20.1 + GregTech Odyssey ** 的模组环境补齐界面，提供亮色 `LightMode` 与暗色 `DarkMode` 两个版本。

## 下载与安装

1. 在 Releases 页下载 `AE-Light-UI-*.zip` 或 `AE-Dark-UI-*.zip`；没有现成产物时也可以克隆本分支自行打包（见下一节）。
2. 把 zip 放进实例的 `minecraft/resourcepacks/` 目录。
3. 游戏内「选项 → 资源包」启用它，并移到列表最上方（否则会被其他资源包覆盖）。
4. 按 `F3 + T` 重载资源。

> 直接把 `LightMode/` 或 `DarkMode/` 文件夹放进 `resourcepacks/` 也可以，效果与 zip 相同。


## 注意事项

- 仅修改 UI 贴图与界面布局，不改变模组逻辑。
- 仅适用于 Minecraft 1.20.x。
- 与其他 AE 风格 UI 资源包互斥，请只启用其中一个。
- 本分支不含语言文件；如果界面文案异常，请检查模组或整合包自带的语言文件，而不是资源包。

