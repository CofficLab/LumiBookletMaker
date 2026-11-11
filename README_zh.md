# LumiBookletMaker

📖 English | [中文版](README_zh.md)

Lumi 与 GameFactory 共享的 Booklet Maker 领域逻辑。

## 当前范围

`BookletMakerCore` 刻意独立于 `LumiKernel`、`LumiProviders`、SwiftUI 以及宿主专属插件代码。目前包含：

- 纸张与小册子设置模型；
- 简单对折、书本折页、签名折页的布局规划；
- 物理纸张分组与页面单元格几何计算；
- PDF 切分点解析与分段规划。

本包是第一层抽取。PDF 检查/渲染、共享 SwiftUI 视图与宿主适配层，将在两个应用就公共领域模型达成一致后才加入。

## 集成方向

```text
LumiBookletMaker
├── BookletMakerCore       # 纯共享领域逻辑
├── BookletMakerServices   # PDF 检查/渲染/拆分
├── BookletMakerUI          # 共享 SwiftUI 视图与视图模型
└── BookletMakerAgent      # 可选的 Agent 工具与 Skill 贡献
```

Lumi 与 GameFactory 应各自保留轻量的插件/装配层。这些层负责内核注册、Rail/Chat/Toolbar 生命周期、插件策略、本地化资源包以及应用专属功能。

## Development

```sh
swift test
```
