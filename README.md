# ppt-zhipu-clouder

<!-- 中文名称：智谱PPT云生成器 —— 自我迭代 · 增加记忆 · 智谱搜索 · 可控交互 -->

A Claude Code skill for creating stunning, animation-rich HTML presentations — from scratch or by converting PowerPoint files.

<!-- 简介：本工具帮助非设计师创建漂亮的网页演示文稿，无需了解CSS或JavaScript。核心特性：自我迭代（AI自我进化）、增加记忆（智能记忆用户偏好）、智谱搜索（集成智谱AI搜索）、可控交互（逐页可控的交互体验） -->

## What This Does

**ppt-zhipu-clouder** helps non-designers create beautiful web presentations without knowing CSS or JavaScript. It uses a "show, don't tell" approach: instead of asking you to describe your aesthetic preferences in words, it generates visual previews and lets you pick what you like.

<!-- 核心理念：采用"展示而非描述"的方法，通过生成视觉预览让用户选择喜欢的风格 -->

### Key Features

<!-- 核心功能：零依赖、视觉风格发现、逐页验证、自我进化记忆、网络搜索集成等 -->


<img width="1296" height="845" alt="截屏2026-04-10 17 36 26" src="https://github.com/user-attachments/assets/01da0c65-e4ce-4b35-aa5f-b06cf35905e7" />
<img width="1282" height="760" alt="截屏2026-04-10 17 36 42" src="https://github.com/user-attachments/assets/5ec9d4c6-6242-4f16-9025-a3d01b2deb1f" />
<img width="1259" height="673" alt="截屏2026-04-10 17 35 11" src="https://github.com/user-attachments/assets/5c83bea9-be53-47c6-ad63-870597827274" />
<img width="1154" height="813" alt="截屏2026-04-10 17 39 44" src="https://github.com/user-attachments/assets/8255f399-4722-4e72-9984-0a27c2d762c8" />



- **Zero Dependencies** — Single HTML files with inline CSS/JS. No npm, no build tools, no frameworks.
  <!-- 零依赖：单个HTML文件，内联CSS/JS，无需npm、构建工具或框架 -->
- **Visual Style Discovery** — Can't articulate design preferences? No problem. Pick from generated visual previews.
  <!-- 视觉风格发现：无法描述设计偏好？从生成的视觉预览中选择即可 -->
- **Slide-by-Slide Verification** — Review and approve each slide individually before final assembly. No surprises.
  <!-- 逐页验证：在最终组装前逐页审查和确认，避免意外 -->
- **Self-Evolving Memory** — Learns your preferences over time and optimizes recommendations for future presentations.
  <!-- 自我进化记忆：随着时间学习您的偏好，优化未来演示文稿的推荐 -->
- **Web Search Integration** — Automatic content research using 智谱AI search for rich, sourced material.
  <!-- 网络搜索集成：使用智谱AI搜索自动进行内容研究，获取丰富、有来源的资料 -->
- **Background Image Support** — Add visual impact with full-bleed background images and automatic overlay handling.
  <!-- 背景图片支持：使用全出血背景图片和自动叠加处理增加视觉冲击力 -->
- **Project Organization** — Automatic directory structure with `public/` for images, `final/` for output, and `websearch.md` for research tracking.
  <!-- 项目组织：自动创建目录结构，public/存放图片，final/存放输出，websearch.md跟踪研究 -->
- **PPT Conversion** — Convert existing PowerPoint files to web, preserving all images and content.
  <!-- PPT转换：将现有PowerPoint文件转换为网页格式，保留所有图片和内容 -->
- **Anti-AI-Slop** — Curated distinctive styles that avoid generic AI aesthetics (bye-bye, purple gradients on white).
  <!-- 反AI平庸：精心策划的独特风格，避免通用的AI美学（告别白色背景上的紫色渐变） -->
- **Production Quality** — Accessible, responsive, well-commented code you can customize.
  <!-- 生产质量：可访问、响应式、注释完善的代码，可供自定义 -->

## Project Structure

<!-- 项目结构：每个演示文稿的组织方式 -->

Each presentation is organized as:

```
my-presentation/
├── websearch.md          # Auto-generated search results and sources
│                         # 自动生成的搜索结果和来源
├── public/               # Your images go here
│                         # 存放您的图片
│   ├── slide-01-bg.jpg
│   └── chart-data.png
├── final/                # Final output
│                         # 最终输出
│   └── index.html        # Complete presentation
│                         # 完整的演示文稿
└── .claude-design/       # Temporary preview files
    └── slide-previews/   # 临时预览文件
```

## Installation

<!-- 安装说明：适用于Claude Code用户 -->

### For Claude Code Users

Copy the skill files to your Claude Code skills directory:

```bash
# Create the skill directory
# 创建技能目录
mkdir -p ~/.claude/skills/ppt-clouder/scripts

# Copy all files (or clone this repo directly)
# 复制所有文件（或直接克隆此仓库）
cp SKILL.md STYLE_PRESETS.md viewport-base.css html-template.md animation-patterns.md ~/.claude/skills/ppt-clouder/
cp scripts/extract-pptx.py scripts/web_search.py ~/.claude/skills/ppt-clouder/scripts/
```

Or clone directly:

```bash
git clone git@github.com:lvye1989/ppt-clouder.git ~/.claude/skills/ppt-clouder
```

Then use it by typing `/ppt-clouder` in Claude Code.
<!-- 然后在Claude Code中输入 /ppt-clouder 使用 -->

## Usage

<!-- 使用方法：创建新演示文稿和转换PPT -->

### Create a New Presentation

<!-- 创建新演示文稿 -->

```
/ppt-clouder

> "I want to create a pitch deck for my AI startup"
```

The skill will:
<!-- 该技能将： -->
1. Ask about your content (slides, messages, images)
   <!-- 询问您的内容（幻灯片、信息、图片） -->
2. Ask about the feeling you want (impressed? excited? calm?)
   <!-- 询问您想要的感觉（印象深刻？兴奋？平静？） -->
3. Generate 3 visual style previews for you to compare
   <!-- 生成3个视觉风格预览供您比较 -->
4. **For each slide**: Ask about layout, images, charts, and content preferences
   <!-- 对于每张幻灯片：询问布局、图片、图表和内容偏好 -->
5. Show you a preview of each slide before proceeding
   <!-- 在继续之前显示每张幻灯片的预览 -->
6. Create the full presentation in your chosen style
   <!-- 以您选择的风格创建完整的演示文稿 -->
7. Organize files in `public/`, `final/`, and `websearch.md`
   <!-- 在 public/、final/ 和 websearch.md 中组织文件 -->
8. Open it in your browser
   <!-- 在浏览器中打开 -->

**Note**: The skill verifies each slide with you before moving to the next. This ensures every slide meets your expectations.
<!-- 注意：该技能在继续下一张之前会与您确认每张幻灯片，确保每张都符合您的期望 -->

### Using Your Own Images

<!-- 使用您自己的图片 -->

When a slide needs images:
<!-- 当幻灯片需要图片时： -->
1. Place your image in the `public/` folder
   <!-- 将图片放入 public/ 文件夹 -->
2. Tell the skill the filename (e.g., "slide-02-bg.jpg")
   <!-- 告诉技能文件名（例如 "slide-02-bg.jpg"） -->
3. The skill will reference it in the presentation
   <!-- 技能将在演示文稿中引用它 -->

### Using Background Images

<!-- 使用背景图片 -->

For dramatic title slides or section transitions, you can use full-bleed background images:
<!-- 对于引人注目的标题幻灯片或章节过渡，您可以使用全出血背景图片： -->

1. Place your image in the `public/` folder
   <!-- 将图片放入 public/ 文件夹 -->
2. The skill automatically adds a semi-transparent overlay for text readability
   <!-- 技能自动添加半透明叠加层以提高文字可读性 -->
3. Background images work with all animations and styles
   <!-- 背景图片适用于所有动画和风格 -->

Example use cases:
<!-- 示例用例： -->
- Title slides for strong first impressions
  <!-- 标题幻灯片，营造强烈的第一印象 -->
- Contextual slides (e.g., Wall Street theme for finance content)
  <!-- 情境幻灯片（例如金融内容的华尔街主题） -->
- Transition slides between major sections
  <!-- 主要章节之间的过渡幻灯片 -->

### Convert a PowerPoint

<!-- 转换PowerPoint -->

```
/ppt-clouder

> "Convert my presentation.pptx to a web slideshow"
```

The skill will:
<!-- 该技能将： -->
1. Extract all text, images, and notes from your PPT
   <!-- 从PPT中提取所有文本、图片和备注 -->
2. Save images to `public/` folder
   <!-- 将图片保存到 public/ 文件夹 -->
3. Show you the extracted content for confirmation
   <!-- 显示提取的内容供您确认 -->
4. Let you pick a visual style
   <!-- 让您选择视觉风格 -->
5. Generate an HTML presentation with all your original assets in `final/`
   <!-- 在 final/ 中生成包含所有原始资源的HTML演示文稿 -->

## Included Styles

<!-- 包含的风格：12种精心策划的视觉预设 -->

### Dark Themes
<!-- 深色主题 -->
- **Bold Signal** — Confident, high-impact, vibrant card on dark
  <!-- 大胆信号：自信、高冲击力、深色背景上的鲜艳卡片 -->
- **Electric Studio** — Clean, professional, split-panel
  <!-- 电动工作室：干净、专业、分屏面板 -->
- **Creative Voltage** — Energetic, retro-modern, electric blue + neon
  <!-- 创意电压：充满活力、复古现代、电光蓝+霓虹 -->
- **Dark Botanical** — Elegant, sophisticated, warm accents
  <!-- 深色植物：优雅、精致、温暖点缀 -->

### Light Themes
<!-- 浅色主题 -->
- **Notebook Tabs** — Editorial, organized, paper with colorful tabs
  <!-- 笔记本标签：编辑风格、有条理、带彩色标签的纸张 -->
- **Pastel Geometry** — Friendly, approachable, vertical pills
  <!-- 粉彩几何：友好、平易近人、垂直胶囊 -->
- **Split Pastel** — Playful, modern, two-color vertical split
  <!-- 分割粉彩：俏皮、现代、双色垂直分割 -->
- **Vintage Editorial** — Witty, personality-driven, geometric shapes
  <!-- 复古编辑：机智、个性驱动、几何形状 -->

### Specialty
<!-- 特色主题 -->
- **Neon Cyber** — Futuristic, particle backgrounds, neon glow
  <!-- 霓虹赛博：未来主义、粒子背景、霓虹光晕 -->
- **Terminal Green** — Developer-focused, hacker aesthetic
  <!-- 终端绿色：面向开发者、黑客美学 -->
- **Swiss Modern** — Minimal, Bauhaus-inspired, geometric
  <!-- 瑞士现代：极简、包豪斯灵感、几何 -->
- **Paper & Ink** — Literary, drop caps, pull quotes
  <!-- 纸墨：文学风格、下沉首字母、引用块 -->

## Architecture

<!-- 架构设计：采用渐进式披露原则 -->

This skill uses **progressive disclosure** — the main `SKILL.md` is a concise map (~180 lines), with supporting files loaded on-demand only when needed:
<!-- 该技能使用渐进式披露——主文件 SKILL.md 是一个简洁的地图（约180行），仅在需要时按需加载支持文件： -->

| File | Purpose | Loaded When |
|------|---------|-------------|
| `SKILL.md` | Core workflow and rules | Always (skill invocation) |
| <!-- SKILL.md --> | <!-- 核心工作流程和规则 --> | <!-- 始终（技能调用时） --> |
| `STYLE_PRESETS.md` | 12 curated visual presets | Phase 2 (style selection) |
| <!-- STYLE_PRESETS.md --> | <!-- 12种精心策划的视觉预设 --> | <!-- 第2阶段（风格选择） --> |
| `viewport-base.css` | Mandatory responsive CSS | Phase 3 (generation) |
| <!-- viewport-base.css --> | <!-- 强制性响应式CSS --> | <!-- 第3阶段（生成） --> |
| `html-template.md` | HTML structure and JS features | Phase 3 (generation) |
| <!-- html-template.md --> | <!-- HTML结构和JS功能 --> | <!-- 第3阶段（生成） --> |
| `animation-patterns.md` | CSS/JS animation reference | Phase 3 (generation) |
| <!-- animation-patterns.md --> | <!-- CSS/JS动画参考 --> | <!-- 第3阶段（生成） --> |
| `scripts/extract-pptx.py` | PPT content extraction | Phase 4 (conversion) |
| <!-- scripts/extract-pptx.py --> | <!-- PPT内容提取 --> | <!-- 第4阶段（转换） --> |
| `scripts/web_search.py` | 智谱AI web search | Phase 1.5 & Phase 3.0a |
| <!-- scripts/web_search.py --> | <!-- 智谱AI网络搜索 --> | <!-- 第1.5阶段和第3.0a阶段 --> |
| `templates/websearch.md.template` | Search record template | Project initialization |
| <!-- templates/websearch.md.template --> | <!-- 搜索记录模板 --> | <!-- 项目初始化 --> |
| `Memory: frontend-slides-runtime-log` | Self-evolving memory system | Phase 0.5 (always read first) & Phase 6 (always update after) |
| <!-- 记忆：ppt-clouder-runtime-log --> | <!-- 自我进化记忆系统 --> | <!-- 第0.5阶段（始终先读取）和第6阶段（始终后更新） --> |

This design follows [OpenAI's harness engineering](https://openai.com/index/harness-engineering/) principle: "give the agent a map, not a 1,000-page instruction manual."
<!-- 此设计遵循OpenAI的驾驭工程原则："给代理一张地图，而不是1000页的说明书。" -->

### Self-Evolving Memory System

<!-- 自我进化记忆系统 -->

The skill maintains a runtime log that learns from each presentation:
<!-- 该技能维护一个运行时日志，从每次演示中学习： -->

- **User Profiles** — Tracks your style preferences and frequently used layouts
  <!-- 用户画像：跟踪您的风格偏好和常用布局 -->
- **Smart Recommendations** — Suggests styles based on topic and past choices
  <!-- 智能推荐：根据主题和过去的选择推荐风格 -->
- **Success Metrics** — Learns which layouts work best for different content types
  <!-- 成功指标：学习哪些布局最适合不同类型的内容 -->
- **Failure Patterns** — Avoids previously problematic design choices
  <!-- 失败模式：避免之前有问题设计选择 -->

After each presentation, the system automatically updates to improve future recommendations.
<!-- 每次演示后，系统会自动更新以改进未来的推荐。 -->

## Environment Setup

<!-- 环境设置 -->

### Core Requirements

<!-- 核心要求 -->

- [Claude Code](https://claude.ai/claude-code) CLI
  <!-- Claude Code 命令行工具 -->
- Python 3.10+ (managed by `uv`)
  <!-- Python 3.10+（由 uv 管理） -->
- `uv` tool for Python environment management
  <!-- 用于Python环境管理的 uv 工具 -->

### Initial Setup (One-time)

<!-- 初始设置（一次性） -->

```bash
# Install uv if not already installed
# 如果尚未安装，请安装 uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# Navigate to skill directory
# 导航到技能目录
cd ~/.claude/skills/ppt-clouder

# Install Python 3.10
# 安装 Python 3.10
uv python install 3.10

# Create virtual environment
# 创建虚拟环境
uv venv --python 3.10 .venv

# Install dependencies
# 安装依赖
uv pip install -p .venv python-pptx zhipuai python-dotenv
```

### Web Search Feature (Optional)

<!-- 网络搜索功能（可选） -->

For automatic content research:
<!-- 用于自动内容研究： -->

1. **Get API Key**: https://open.bigmodel.cn/usercenter/apikeys
   <!-- 获取API密钥 -->
2. **Set environment variable**:
   <!-- 设置环境变量： -->
   ```bash
   export ZHIPU_API_KEY='your-api-key-here'
   ```
3. **Or create .env file**:
   <!-- 或创建 .env 文件： -->
   ```bash
   echo 'ZHIPU_API_KEY=your-api-key-here' > ~/.claude/skills/ppt-clouder/.env
   ```

**Search Configuration Options:**
<!-- 搜索配置选项： -->
- **Search Engine**: `search_pro` (recommended), `search_pro_sogou`, `search_std`
  <!-- 搜索引擎：search_pro（推荐）、search_pro_sogou、search_std -->
- **Content Size**: `high` (detailed), `medium` (brief)
  <!-- 内容大小：high（详细）、medium（简要） -->
- **Recency Filter**: `oneDay`, `oneWeek`, `oneMonth`, `oneYear`, `noLimit`
  <!-- 时间过滤：oneDay（一天）、oneWeek（一周）、oneMonth（一月）、oneYear（一年）、noLimit（无限制） -->

## Philosophy

<!-- 设计理念 -->

This skill was born from the belief that:
<!-- 该技能诞生于以下信念： -->

1. **You don't need to be a designer to make beautiful things.** You just need to react to what you see.
   <!-- 您不需要成为设计师就能创造美丽的事物。您只需要对您看到的做出反应。 -->

2. **Dependencies are debt.** A single HTML file will work in 10 years. A React project from 2019? Good luck.
   <!-- 依赖是债务。单个HTML文件10年后仍能工作。2019年的React项目？祝你好运。 -->

3. **Generic is forgettable.** Every presentation should feel custom-crafted, not template-generated.
   <!-- 通用是容易被遗忘的。每个演示文稿都应该感觉像是定制制作的，而不是模板生成的。 -->

4. **Comments are kindness.** Code should explain itself to future-you (or anyone else who opens it).
   <!-- 注释是友善的。代码应该向未来的您（或任何打开它的人）解释自己。 -->

5. **Organization matters.** Clear directory structures (`public/`, `final/`, `websearch.md`) make projects maintainable.
   <!-- 组织很重要。清晰的目录结构（public/、final/、websearch.md）使项目可维护。 -->

## Requirements

<!-- 要求 -->

- [Claude Code](https://claude.ai/claude-code) CLI
- See [Environment Setup](#environment-setup) for Python/uv requirements
  <!-- 查看环境设置了解Python/uv要求 -->

## Credits

<!-- 致谢 -->

基于[@zarazhangrui](https://github.com/zarazhangrui)进行优化升级
<!-- Based on @zarazhangrui, optimized and upgraded -->

迭代技术由 [ppt-clouder](https://github.com/lvye1989/ppt-clouder) 提供。
<!-- Iteration technology provided by ppt-clouder -->

Inspired by the "Vibe Coding" philosophy — building beautiful things without being a traditional software engineer.
<!-- 受"氛围编程"理念启发——无需成为传统软件工程师就能构建美丽的事物。 -->

## License

<!-- 许可证 -->

MIT — Use it, modify it, share it.
<!-- MIT许可证——使用它、修改它、分享它。 -->
