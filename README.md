# 🌙 Luna Anki 模板说明

简洁双栏布局的日语/多语言卡片模板，支持可拖拽分隔条、词典多标签页、例句与备注格式化、夜间模式适配等。

<img width="2940" height="1846" alt="image" src="https://github.com/user-attachments/assets/8b2ca638-a60a-41e6-a068-6cc8e555828e" />

<img width="2940" height="1846" alt="image" src="https://github.com/user-attachments/assets/2974b4ff-e407-4738-84c6-cb52856844ca" />

## 🗂️ 文件结构
- `luna/Front.template.txt`：正面模板，显示单词与假名/注音。
- `luna/Back.template.txt`：反面模板，包含例句、备注、截图、词典标签页和拖拽分隔条逻辑。
- `luna/Styling.txt`：样式表（浅色/夜间主题、表格、标签、分隔条等）。

## ✨ 基础功能
- **双栏布局**：左侧主内容，右侧词典；<800px 或单栏模式时自动堆叠。
- **可拖拽分隔条**：双栏时在两 pane 之间显示，拖动调整左右比例，写入 `localStorage`（键 `luna_split_ratio_v1`），切换卡片后保留；竖排时为横向拖动条。
- **注音智能隐藏**：有 ruby 时隐藏原词，无 ruby 时反之。
- **音频点击播放**：点击单词/例句触发对应音频。
- **例句/图片/备注自动隐藏**：字段为空或无子元素时自动 `display: none`，保持版面整洁。
- **备注自动编号**：多行备注自动生成①②③…前缀，行内安全转义。
- **词典多标签页**：`dictionaryInfo` + `dictionaryContent` 动态生成 tab，支持 tab 切换、脚本执行；无词典时自动单栏。
- **mdict 内部样式**：当存在 `.tab-pane_mdict_internal.active` 时应用备注样式；若不存在，则对 `#tab_contents` 应用。
- **夜间模式**：跟随 Anki `nightMode`，调整背景、文本、图片滤镜等。
- **表格/标签/链接**：预设表格配色、Tag 样式、链接 hover 效果。

## 🖥️ 使用方法
1. 在 Anki「管理笔记类型」中打开模板编辑器。
2. 将 `Front.template.txt` / `Back.template.txt` / `Styling.txt` 内容分别粘贴到对应面板和样式栏，保存。
3. 若已有旧模板，保存后需重新打开预览或切换卡片以刷新样式。

## 🔧 可用字段
- `word` / `rubytextHtml`：单词与注音。
- `example_sentence` / `audio_for_example_sentence`：例句与音频。
- `remarks`：备注（多行自动编号）。
- `screenshot`：图片/截图。
- `dictionaryInfo` / `dictionaryContent`：词典标签页数据。

## 🎨 样式要点
- 颜色/圆角：通过 CSS 变量集中定义，可在 `:root` 调整。
- 分隔条配色：浅色 `rgba(247, 244, 237, 0.8)`，夜间 `rgba(62, 56, 65, 0.6)`，悬停加深。
- 间距：`--pane-gap` 控制布局间距，竖屏固定为 `0.8em`。

## ❓ 常见问题
- **拖拽分隔条不显示**：仅双栏且词典可见时显示；单栏或隐藏词典时自动隐藏。
- **样式未刷新**：确保保存模板后重新打开预览或切换卡片。若外部修改文件，需要再次粘贴到 Anki 内。

## 😘 相关项目
- [LunaTranslator](https://github.com/HIllya51/LunaTranslator)
- [anki-quizify](https://github.com/e-chehil/anki-quizify)

## ❤️ 来赞助我
 ![IMG_5311](https://github.com/user-attachments/assets/93e219ac-345d-4e5d-9a03-19a11e77c15f)

Enjoy your study! 🚀
