# pptx__viewing

**一个 Claude Code Skill**，用于读取 PDF/PPTX 课件，自动筛选重要页面截图，生成一份以解释为主的 Obsidian Markdown 笔记。

---

## 它能做什么

不是简单地把每页截图堆在一起，而是真正「读懂」课件后再写笔记：

1. 提取全部文字，整体理解内容和难度
2. 把每页渲染成图片并全部看一遍
3. **只保留重要的图**——根据课件难度动态调整比例（入门约30%，中等约50%，较难约60-70%）
4. 用自己的话写解释，不复述 PPT 原文
5. 写完后自动删掉未引用的图片，输出目录保持整洁

输出的是一份可以直接拿来复习的笔记，不是课件的截图合集。

---

## 安装

```bash
npx skills add lyuyao59/pptx-viewing-skill@pptx__viewing
```

---

## 使用方式

直接用中文告诉 Claude Code：

- `帮我看一下这个PPT` + 文件路径
- `把这个课件整理成笔记，放到 D:\xxx 里`
- `这个PDF我看不懂，帮我生成图文讲解`

---

## 依赖

需要 Python 环境，并安装 PyMuPDF：

```bash
pip install pymupdf
```

如果要处理 PPTX 文件，建议先用 LibreOffice 转成 PDF：

```bash
# macOS
brew install libreoffice

# Windows（下载安装包）
# https://www.libreoffice.org/download/download/
```

---

## 输出结构

```
输出目录/
├── 文件名_笔记.md          ← 笔记正文，使用 Obsidian ![[]] 图片语法
└── 文件名_images/
    ├── page_03.png         ← 只有笔记中实际引用的页面
    ├── page_07.png
    └── ...
```

---

## License

MIT
