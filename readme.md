# QDU Math in Lean - 文档浏览器

Markdown 文档浏览器，专为数学和 Lean 4 文档设计。
用来展示以及分享 **QDU math in lean** 团队 产出的成果以及技术文档

## 在线访问

本项目已部署到 GitHub Pages：

**https://qdu-math-in-lean.github.io/**

## 本地使用

### 方法 1: 使用提供的脚本

```bash
# 使用 start.sh
./start.sh

# 或使用 server.py
python3 server.py
```

### 方法 2: 使用 Python HTTP 服务器

```bash
# 克隆仓库
git clone https://github.com/QDU-Math-in-lean/web_viewer.git
cd web_viewer

# 启动本地服务器
python3 -m http.server 8000

# 在浏览器中访问
# http://localhost:8000/
```



## 添加新文档

1. 在 `sources/` 目录下添加或修改 `.md` 文件
2. 运行更新脚本：
   ```bash
   python3 generate_filelist.py
   ```
3. 提交并推送到 GitHub：
   ```bash
   git add .
   git commit -m "添加新文档"
   git push
   ```

## Wiki 链接语法

### 文件间跳转
使用 `[[文件名]]` 链接到其他文档：
```markdown
详见 [[如何写lean]] 和 [[策略汇总]]
```

### 页面内跳转
使用 `[[#标题名]]` 跳转到当前页面的标题：
```markdown
参考 [[#安装步骤]] 部分
```

## 项目结构

```
.
├── index.html              # 主页面（浏览器）
├── generate_filelist.py    # 文件列表生成脚本
├── server.py              # 本地开发服务器
├── start.sh               # 启动脚本
├── sources/               # Markdown 文档目录
│   ├── hello.md
│   ├── lean/
│   ├── 策略/
│   ├── 环境以及配置问题/
│   └── 初等数论形式化/
└── .github/
    └── workflows/
        ├── update-filelist.yml  # 自动更新文件列表
        └── deploy-pages.yml     # 部署到 GitHub Pages
```
## 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 相关链接

- [Lean 4 官方文档](https://lean-lang.org/)
- [Mathlib4 文档](https://leanprover-community.github.io/mathlib4_docs/)
- [Marked.js](https://marked.js.org/) - Markdown 解析器
