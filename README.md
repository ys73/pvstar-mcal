# 斜屋面光伏安装系统计算器

支持 Clenergy、Kseng、PVSTAR 三个品牌的斜屋面光伏支架配件数量计算工具。

## 项目结构

```
pvstar-calculator/
├── index.html    # 主计算器（含所有样式、逻辑、图片）
├── admin.html    # PVSTAR 配件数据后台管理
└── README.md
```

## 本地使用

直接双击 `index.html` 即可，无需服务器。

## Claude Code 开发

```bash
cd pvstar-calculator
claude
```

然后用自然语言描述要修改的内容，Claude Code 会直接编辑文件。

每次重要改动后建议提交：
```bash
git add .
git commit -m "描述这次改了什么"
```

## 工作流程

1. 双击 `index.html` → 选择 PVSTAR → 点击「⚙ 数据维护」进入后台
2. 在 `admin.html` 维护配件数据
3. 点击「🚀 生成独立计算器」→ 下载含最新数据的独立 HTML 文件

## 计算公式说明

### PVSTAR（n = 每排组件数）
| 配件 | 公式 |
|------|------|
| 导轨 | 每块 ×1 |
| 挂钩 | 每排 2×(n+1) |
| 侧压块 | 每排 4 |
| 中压块 | 每排 2×(n-1) |
| 导轨连接件 | ≤2→0，≥3→每排 2×round(n/2)-2 |
| 导轨端盖 | 每排左2+右2（共2对） |

> 每排超过 12 片时建议断开另起一排，避免热胀冷缩变形。
