---
hide:
  - navigation
comments: true
---
# CHANGELOG

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

这个项目的所有显著变化都将记录在这个文件中。

格式基于 [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)，以及这个项目遵循 [Semantic Versioning](https://semver.org/spec/v2.0.0.html)。

## [0.2.0-beta] - 2025-06-26

- Beta 阶段不保证向前兼容，删除旧版本再导入

### Added

- `[Important]` 新增 `ScriptDocGen` 文档工具，给定一个 `Type` 类型的值，即可一键生成 Markdown 格式的文档，可选 Scripting API 或者 Complete References，默认支持 mkdocs-material，页面支持双语切换，支持多文档批量生成。更多信息查看使用文档
- 新增 `YuumixEditor` 程序集，等同于 `UnityEditor` 程序集，仅在编辑器可用，需要使用 `#if UNITY_EDITOR` 宏定义
- `Common 部分` 新增 `InspectorMultiLanguage` 模块，核心类 `InspectorMultiLanguageManagerSO`，实现 `Inspector` 多语言支持，目前仅支持中文和英语
- 新增 `MultiLanguageButtonAttribute`，添加此特性到方法上，可以支持多语言按钮，等同于 `ButtonAttribute`，但是此特性目前无法实时切换语言
- 新增 `MultiLanguageTextAttribute`，添加此特性，可以支持多语言文本，等同与 `LabelTextAttribute`，兼容 `Odin Inspector` 绘制系统，支持实时切换
- 新增 `MultiLanguageTitleAttribute`，添加此特性，可以支持多语言标题，等同与 `LabelTitleAttribute`，兼容 `Odin Inspector` 绘制系统，支持实时切换
- 新增 `MultiLanguageCommentAttribute`，添加此特性，可以支持多语言注释，兼容 `Odin Inspector` 绘制系统，支持实时切换
- 新增 `MultiLanguageInfoBoxAttribute`，添加此特性，可以支持多语言信息框，等同与 `InfoBoxAttribute`，兼容 `Odin Inspector` 绘制系统，支持实时切换
- 新增 `ShowIfChineseAttribute`，等同于 ` [ShowIf("InspectorMultiLanguageManagerSO.IsChinese", false)]`，当 `Odin Toolkits` 配置为中文时，才显示添加了此特性的成员
- 新增 `ShowIfEnglishAttribute`，等同于 ` [ShowIf("InspectorMultiLanguageManagerSO.IsEnglish", false)]`，当 `Odin Toolkits` 配置为英语时，才显示添加了此特性的成员
- 新增 `Wigdet` 控件功能，基于 `InspectorMultiLanguage` 模块，把特殊的 `Inspector` 绘制封装成独立的控件类，需要时直接新增字段即可。
- 新增 `MultiLanguageButtonWidget`，提供多语言的按钮控件字段，兼容 `Odin Inspector` 绘制系统，支持实时切换，使用时必须添加 `[MultiLanguageButtonWidgetConfigAttribute]` 特性进行配置
- 新增 `MultiLanguageDisplayWidget`，提供多语言的文本控件字段，兼容 `Odin Inspector` 绘制系统，支持实时切换，使用时必须添加 `[MultiLanguageDisplayWidgetConfigAttribute]` 特性进行配置
- 新增 `MultiLanguageHeaderWidget`，多语言的头部说明控件，用于模块的简单介绍，兼容 `Odin Inspector` 绘制系统，支持实时切换，使用构造函数进行内部配置
- 新增 `MultiLanguageFooterWidget`，多语言的页脚控件，为模块补充一些信息，提供贡献者列表和补充说明，兼容 `Odin Inspector` 绘制系统，支持实时切换，使用构造函数进行配置
- 新增两个语言切换按钮控件 `SwitchInspectorLanguageWidget` 和 `EnumLanguageWidget`，提供多语言切换按钮，依赖 `Odin Inspector` 绘制系统，支持实时切换
- 新增多个 `MenuItem`，`HelpWindow` 菜单提供 `Odin Toolkits` 补充帮助，`WIPTempHubWindow` 用于收集整体暂时没有独立划分模块的临时功能
- 新增 `Utilities` 模块的 `StaticExtensions` 静态扩展部分，目前包括 `TypeExtensions, StringExtensions`
- 新增 `Prototype` 模块，提供原型需要的内容，目前包含一份公开的美术资源 `Undead Survivor` 包，作者 `Gold Metal`，实际项目打包时可以直接移除
- 新增2个 `TemplateCodeGen` 模块代码模板，`RuntimeOdinSerializedMonoBehaviourTemplate.txt` 和 `RuntimeOdinSerializedScriptableObjectTemplate.txt`
- 新增特殊自定义类 `InterfaceReference`，在 `Inspector` 面板限制必须实现特定接口
- 新增两个 `ScriptableSingleton` 使用方法模板，位于 `Common` 文件夹下
- 新增 `OdinToolkitsData` 文件夹，`Odin Toolkits` 生成的配置数据资源默认目录，不存在时会自动生成
- `[For Contributors]` 新增多个内部只读多语言数据结构体，`MultiLanguageData`， `MultiLanguageTitleData`，`ButtonAttributeData` 用于存储多语言数据，用户可以使用其进行其他特性的扩展。
- `[For Contributors]` 新增 `Work In Progress` 模块，用于收集未整理成独立模块的功能，非正式模块，随时可能移除。实际项目打包时可以直接移除，**此部分不接受贡献**
- `[For Contributors]` 新增 `MenuItemGlobalSettings` 统一管理 `MenuItem`

### Changed

- 修改命名空间规范，尽量简短，最后一个终止在模块名称，或者 `Editor，Runtime，Test` 等特殊名词，此规则不包括 `Work In Progress` 模块
- 修改 `MenuItem` 顺序设计
- 修改 `GenerateTemplateCodeTool` 模块名称为 `TemplateCodeGen`，更简洁，清晰
- 对现有模块部分使用 `MultiLanguageCommentAttribute` 补充多语言注释
- 精简 `Singleton` 单例模块，移除整合不常用的功能
- 修改 `EditorSettings` Window 菜单，提供一个编辑器阶段设置的窗口，整合不同模块的编辑器阶段的设置

## [0.1.3.beta] - 2025-05-21

- Beta 阶段不保证向前兼容，删除旧版本再导入

### Added

- 新增 `SwitchButtonAttribute`，将 `bool` 显示为开关，兼容 `ToggleLeftAttribute` 特性 - 修改自 `Schwapo` 开源项目
- 新增 `Singleton` 单例模块

### Changed

- 完善生成模板代码工具 `GenerateTemplateCode`，并完善 `OdinToolkits` 文档网站信息
- 调整菜单路径
- 调整 `OdinToolkits` 文件夹定位，支持 `OdinToolkits` 文件夹整体移动
- 调整 `Common` 文件夹
- 完善 `QuickGenerateSO` 文档信息

### Removed

- `ComponentBinder`，组件绑定工具，在项目中并未完善，无法使用
- 移除 `OdinToolkits` 编辑器配置，未修改完善

## [0.1.2.beta] - 2025-05-09

### Changed

- Beta 阶段不向前兼容
- 重新设计项目结构，根目录为 Plugins/Yuumix/OdinToolkits，将 SO 框架移至 OdinToolkits 文件夹内。

## [0.1.1] - 2025-04-28

### Added

- 新增两个第三方引用，位于 ThirdParty 文件夹，包括一个[Odin 相关开源库](https://github.com/Schwapo/Odin-Resolved-Parameters-Overview)和一个[Log相关免费资源](https://rubickanov.itch.io/)
- 新增 Odin 自带特性解析手册，中文解析 Odin 默认提供的 Attributes，比官方的手册更适合中文开发者。
- 新增模版代码生成工具
- 新增 ComponentBinder ，组件绑定工具
- 新增 OdinToolkits 编辑器配置
- 新增自定义扩展 Odin Attribute
- 新增提取 Odin Syntax Highlight 资源文件，让 Odin 的语法高亮为开发者所用
- 新增通用模块 Common，一些跨项目通用类，方法

## [0.1.0] - 2025-04-21

### Added

- 新增一个简单工具，QuickGenerateSO - 快速右键生成 SO 资源，自动遍历选择的资源，根据继承了 `ScriptableObject` 的脚本，生成 SO 资源。
