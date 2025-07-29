---
hide:
  - navigation
comments: true

---

# README

## 简介

`Odin Toolkits For Unity` 是依赖 Unity 插件 `Odin Inspector and Serializer`（以下简称为 `Odin Inspector` ）的第三方扩展工具集，开源项目，模块化设计，积累对整个项目低侵入性的解决方案，按需使用。

`GitHub` 项目链接: [OdinToolkits-For-Unity](https://github.com/Yuumi-Zeus/OdinToolkits-For-Unity)

`Unity AssetStore` 网站链接：[AssetStore Odin Inspector](https://assetstore.unity.com/packages/tools/utilities/odin-inspector-and-serializer-89041)

`Odin Inspector` 官网链接：[Sirenix Odin Inspector](https://odininspector.com/)

## 项目愿景

- 成为使用 `Odin Inspector` 的开发者的首选工具包。
- 能够帮助开发者快速学习使用 `Odin Inspector`，发挥其更多的价值，而不是仅了解官方提供的 `Attribute`。
- 能够提供更多优雅的，效率高的解决方案。

## 项目适合的人群

- 拥有 `Odin Inspector` 的开发人员，可以提供更多的解决方案。
- 准备进行开发 `Unity 编辑器扩展` 的人员，可以有更多的案例参考。
- 只想使用官方提供的 `Attribute`，但是对 `Odin Inspector` 提供的特性使用方法不熟悉的 **使用中文的开发者**，内部包含 `Attribute` 中文解析窗口。
- 想进行插件开发的人员，提供了部分工具和参考，包括 API 文档，网页方案（此项目）。
- 使用 `Rider` 的 `Unity` 开发人员，`Odin Inspector` 和 `Rider` 达成了初步合作。

## 项目结构

``` title="项目树形结构图"
Plugins/
│  ├─ Yuumix/
│  │  ├─ OdinToolkits/
│  │  │  ├─ Community/
│  │  │  │  ├─ Editor/
│  │  │  │  ├─ Modules/
│  │  │  ├─ Editor/
│  │  │  │  ├─ Core/
│  │  │  │  ├─ Modules/
│  │  │  │  ├─ Shared/
│  │  │  ├─ Runtime/
│  │  │  │  ├─ Core/
│  │  │  │  ├─ Modules/
│  │  │  │  ├─ Resources/
│  │  │  │  ├─ Shared/
│  │  │  │  ├─ YuumixEditor/
│  │  ├─ CHANGELOG.md
```

!!! tip

    感谢你看到这里，如果 Odin Toolkits 在你的 Unity 开发中切实提供了帮助，恳请为项目点亮一颗 ★ Star！
    
    你的每一份支持都是我在业余时间持续维护、迭代项目的最强动力。
    
    如果 Odin Toolkits 打包出现错误，或者代码规范不符合要求，请提 issue，或者留言给我，我会及时处理。
