# Dev JSON Swiss Knife · JSON 全能瑞士军刀

[English](#english) | [中文](#中文)

🚀 **在线体验 / Live Demo:** [https://kinborough.github.io/dev-json-swiss-knife/](https://kinborough.github.io/dev-json-swiss-knife/)

📦 **源码仓库 / Repository:** [https://github.com/Kinborough/dev-json-swiss-knife](https://github.com/Kinborough/dev-json-swiss-knife)

一个纯前端、零依赖、离线可用的 JSON 全能工具箱：格式化 · 语法诊断 · 交互式树视图 · JSONPath 复制 · TypeScript / Python / Go 类型生成 · YAML 转换 · 实时统计。

---

## 中文

### 一、设计参考案例（致谢 / Acknowledgements）

本项目是 [daily-tools-factory](https://github.com/Kinborough)「高星开源工具对标复刻计划」的第 1 个作品，交互与功能设计参考了以下优秀开源项目：

| 参考项目 | 借鉴点 |
| --- | --- |
| [CorentinTh/it-tools](https://github.com/CorentinTh/it-tools) | 单页多工具布局、深色极客风配色、一键示例数据与格式化模块交互 |
| [AykutSarac/jsoncrack.com](https://github.com/AykutSarac/jsoncrack.com) | JSON 树状/图状可视化、节点点击交互体验 |
| [gchq/CyberChef](https://github.com/gchq/CyberChef) | 「瑞士军刀」式一体化工具箱产品哲学 |
| [iib0011/omni-tools](https://github.com/iib0011/omni-tools) | 纯浏览器端本地处理、零上传隐私承诺 |
| [callumlocke/json-formatter](https://github.com/callumlocke/json-formatter) | 即时格式化与可读性优先的排版思路 |

### 二、核心功能清单

**左侧输入区（Input）**
1. 任意粘贴 / 拖拽文件 / 点击上传（`.json`、`.txt`）载入 JSON。
2. 语法错误**行号 + 列号精确定位**，输出上下 2 行上下文并用 `^` 标出出错位置。
3. 智能修复提示：单引号、尾随逗号、多余括号、未转义字符、`position N` 到行列自动换算等 8 类常见错误逐一给出中文解决方案。
4. 一键填入**复杂嵌套示例数据**（含 5 层嵌套、空对象、空数组、null、布尔、浮点、emoji、数组对象混合）。
5. 美化（2 / 4 空格 / Tab 缩进切换）与压缩一键切换，附键名递归排序、复制原文。
6. 快捷键：`Ctrl/Cmd + Shift + F` 美化，`Ctrl/Cmd + Shift + M` 压缩。

**右侧多标签功能区（Output）**

7. 🌳 **树状视图**：可折叠 / 展开的交互式 JSON 树，按类型着色（字符串绿、数字橙、布尔紫、容器蓝），支持全部展开 / 全部折叠 / 键名过滤，**点击任意节点即一键复制其 JSONPath**（如 `$.benchmarks[0].tags[1]`）。
8. 🧬 **类型生成**：一键生成 **TypeScript Interface**、**Python Dataclass**、**Go Struct**，数组对象自动合并同类结构、字段带 `json:"..."` tag、可复制或下载 `.ts` / `.py` / `.go` 文件。
9. 📄 **YAML**：实时 JSON → YAML 转换，正确处理嵌套数组、空对象 `{}`、空数组 `[]`、特殊字符自动加引号、保留键名原样，可复制或下载 `.yaml`。
10. 🧭 **路径列表**：枚举全量 JSONPath 及对应类型与值预览，支持过滤、点击复制、一键复制全部路径。
11. 顶部状态胶囊实时显示「✓ JSON 有效 / ✕ JSON 无效 / ● 等待输入」。

**底部实时统计（Live Stats）**

12. 字符数、UTF-8 体积（B / KB / MB 自适应）、**最大嵌套深度**、**键数量**、元素总数、根节点类型 —— 输入即算，无需点击。

### 三、技术栈

- 单文件 `index.html`，**零构建步骤**，双击即可运行。
- [TailwindCSS CDN](https://cdn.tailwindcss.com) 负责样式，原生 JavaScript 负责全部逻辑。
- 数据与逻辑 100% 在本地浏览器执行，**没有任何网络请求、没有任何数据上传**。

### 四、本地使用

```bash
git clone https://github.com/Kinborough/dev-json-swiss-knife.git
cd dev-json-swiss-knife
# 直接双击 index.html，或用任意静态服务器：
npx serve .
```

---

## English

### 1. Design References (Acknowledgements)

This is the **first** deliverable of the [daily-tools-factory](https://github.com/Kinborough) "high-star open-source tool replication plan". Interaction and feature design reference these excellent projects:

| Project | What we learned |
| --- | --- |
| [CorentinTh/it-tools](https://github.com/CorentinTh/it-tools) | Single-page multi-tool layout, dark geek palette, one-click sample data & formatter module |
| [AykutSarac/jsoncrack.com](https://github.com/AykutSarac/jsoncrack.com) | JSON tree/graph visualization and click-to-inspect node interaction |
| [gchq/CyberChef](https://github.com/gchq/CyberChef) | The "swiss knife" all-in-one toolbox philosophy |
| [iib0011/omni-tools](https://github.com/iib0011/omni-tools) | Pure client-side processing, zero-upload privacy promise |
| [callumlocke/json-formatter](https://github.com/callumlocke/json-formatter) | Instant formatting with readability-first typography |

### 2. Feature Checklist

**Left panel (Input)**
1. Paste, drag-and-drop, or upload (`.json`, `.txt`) any JSON payload.
2. Syntax errors pinpointed by **line + column**, with 2 lines of surrounding context and a `^` caret marker.
3. Smart fix hints for 8 common error classes: single quotes, trailing commas, extra brackets, bad escape chars, `position N` → line/column conversion, and more — each with a concrete fix in Chinese.
4. One-click **deeply nested sample data** (5 nesting levels, empty object, empty array, `null`, booleans, floats, emoji, mixed array-of-objects).
5. Pretty-print (2 / 4 spaces / Tab) and minify in one click, plus recursive key sorting and raw copy.
6. Shortcuts: `Ctrl/Cmd + Shift + F` pretty, `Ctrl/Cmd + Shift + M` minify.

**Right panel (Tabbed output)**
7. 🌳 **Tree View**: collapsible/expandable interactive JSON tree, type-colored (string green, number amber, boolean fuchsia, container sky), with expand-all / collapse-all / key filtering, and **click any node to copy its JSONPath** (e.g. `$.benchmarks[0].tags[1]`).
8. 🧬 **Type Generator**: one-click **TypeScript Interface**, **Python Dataclass**, and **Go Struct**; array objects merge their shapes, Go fields carry `json:"..."` tags, output is copyable and downloadable as `.ts` / `.py` / `.go`.
9. 📄 **YAML**: live JSON → YAML conversion handling nested arrays, `{}` / `[]` empties, auto-quoting of special scalars and key preservation; copy or download `.yaml`.
10. 🧭 **Path List**: full JSONPath inventory with type and value preview, filterable, click-to-copy, copy-all.
11. Status pill shows `✓ JSON valid` / `✕ JSON invalid` / `● waiting` in real time.

**Bottom live stats**
12. Character count, UTF-8 size (B / KB / MB), **max nesting depth**, **key count**, total element count, and root node type — computed on every keystroke.

### 3. Tech Stack

- Single `index.html` file, **no build step**, just double-click to run.
- [TailwindCSS CDN](https://cdn.tailwindcss.com) for styling, vanilla JavaScript for all logic.
- 100% local execution: **no network requests, no data ever leaves your browser**.

### 4. Local Usage

```bash
git clone https://github.com/Kinborough/dev-json-swiss-knife.git
cd dev-json-swiss-knife
# Double-click index.html, or serve it statically:
npx serve .
```

---

## License

[MIT](./LICENSE) © 2026 Kinborough
