---
title: 写作指南：Hexo 与 Butterfly 常用写法
date: 2026-10-11 03:00:00
updated: 2026-10-11 03:00:00
tags:
  - Hexo
  - 教程
categories:
  - 技术
  - 博客搭建
---

这篇文章演示本站支持的常用写法，你可以直接复制本文的源码改成自己的内容。

<!-- more -->

## 一、这篇文件的源码在哪

打开 `source/_posts/writing-guide.md` 就能看到本文的全部源码，对照着看最直观。

## 二、front-matter 必填项

```yaml
---
title: 写作指南：Hexo 与 Butterfly 常用写法
date: 2026-10-11 03:00:00     # 必须写！决定文章 URL，别删
updated: 2026-10-11 03:00:00  # 可选，不写则不显示"更新于"
tags:
  - Hexo
  - 教程
categories:
  - 技术
  - 博客搭建
---
```

`date` 一旦确定就**不要改**，改了这个链接就变了，旧链接全部失效。

## 三、摘要分割线

上面那行 `<!-- more -->` 就是摘要分隔符。它之前的内容会显示在首页卡片上，之后的内容需要点进文章才能看到。

## 四、标题与文本

```markdown
## 二级标题
### 三级标题

**加粗**、*斜体*、~~删除线~~、`行内代码`

[站外链接](https://hexo.io/)
```

## 五、代码块

标准 Markdown 写法，自动高亮并带复制按钮：

```javascript
function greet(name) {
  // Butterfly 会自动识别语言并高亮
  return `你好，${name}`
}
console.log(greet('世界'))
```

```yaml
# YAML 同样支持
site:
  title: 尹俊杰de博客
  language: zh-CN
```

## 六、提示框

```markdown
{% note info %}
信息提示框
{% endnote %}

{% note warning %}
警告提示框
{% endnote %}
```

实际效果：

{% note info %}
这是 info 提示框。可选类型：`info`、`warning`、`danger`、`success`、`primary`、`default`。
{% endnote %}

{% note warning %}
这是 warning 提示框，适合写注意事项。
{% endnote %}

## 七、表格

```markdown
| 命令 | 作用 |
|---|---|
| `hexo new` | 新建文章 |
```

| 命令 | 作用 |
|---|---|
| `npx hexo new "标题"` | 新建文章 |
| `npx hexo server` | 本地预览 |
| `git push` | 发布上线 |

## 八、图片

因为已开启 `post_asset_folder`，每篇文章有独立资源目录 `source/_posts/写作指南.../`。图片放进去后用：

```markdown
{% asset_img sample.png 这是一张示例图片 %}
```

实际效果：

{% asset_img sample.png 示例图片，放在文章同名资源目录中 %}

## 九、列表与引用

- 无序列表项
  - 嵌套项
- 第二项

1. 有序列表
2. 第二项

> 这是一段引用文字，左侧会有竖线装饰。

## 十、折叠块

```markdown
{% hideToggle 点我展开 %}
被折叠起来的内容
{% endhideToggle %}
```

{% hideToggle 点我展开看隐藏内容 %}
这里是被折叠的内容，点击标题即可展开或收起。
{% endhideToggle %}

---

以上就是常用写法。更多标签语法见 [Butterfly 官方文档](https://butterfly.js.org/)。
