<!-- markdownlint-disable-file MD033 MD041 -->
<h1 align="center">shortcode-missing-translation | FixIt</h1>

<img width="810" alt="image" src="https://github.com/user-attachments/assets/a18d2888-0f5d-4c82-929e-c79b6465c04a" />
<img width="810" alt="image" src="https://github.com/user-attachments/assets/7868c724-8bbd-4336-b43d-4ed607019988" />

<div align="center" class="ignore">
  <p>用于多语言站点，缺少翻译时暂时以指定的语言呈现当前页面翻译的内容。</p>
  简体中文 |
  <a href="https://fixit.lruihao.cn/zh-cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=chinese_traditional">繁體中文</a> |
  <a href="/README.en.md">English</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=french">Français</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=russian">Русский язык</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=spanish">Español</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=hindi">हिन्दी</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=deutsch">deutsch</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=korean">한국어</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=japanese">しろうと</a>
</div>

## 要求

适用于所有 Hugo 主题。

## 安装组件

安装方式与 [安装主题](https://fixit.lruihao.cn/zh-cn/documentation/installation/) 相同，有多种安装方式，任选一种即可，这里介绍两种主流方式。

### 作为 Hugo 模块安装

首先确保你的项目本身是一个 [Hugo 模块](https://gohugo.io/hugo-modules/use-modules/#initialize-a-new-module)。

然后将此主题组件添加到你的 `hugo.toml` 配置文件中：

```toml
[module]
  [[module.imports]]
    path = "github.com/hugo-fixit/FixIt"
  [[module.imports]]
    path = "github.com/hugo-fixit/shortcode-missing-translation"
```

在 Hugo 的第一次启动时，它将下载所需的文件。

要更新到模块的最新版本，请运行：

```bash
hugo mod get -u
hugo mod tidy
```

### 作为 Git 子模块安装

将 [FixIt](https://github.com/hugo-fixit/FixIt) 和此 git 存储库克隆到你的主题文件夹中，并将其作为网站目录的子模块添加。

```bash
git submodule add https://github.com/hugo-fixit/FixIt.git themes/FixIt
git submodule add https://github.com/hugo-fixit/shortcode-missing-translation.git themes/shortcode-missing-translation
```

接下来编辑项目的 `hugo.toml` 并将此主题组件添加到你的主题中：

```toml
theme = ["FixIt", "shortcode-missing-translation"]
```

## 配置

```toml
[gitInfo]
  repo = "https://github.com/hugo-fixit/docs"
  branch = "main"
  # 相对于仓库根目录的内容目录路径
  dir = "content"
```

## 使用 Shortcode

以下是一个使用示例：

```markdown
{{< missing-translation >}}
```

> [!TIP]
> 请至少保证有一个语言的翻译内容，如果有多个语言的翻译内容，默认选择第一个翻译内容。

或者，指定已有翻译语言：

```markdown
{{< missing-translation "en" >}}
```

是否在虚线框内呈现原始内容，默认值为 `true`。

```markdown
{{< missing-translation original=false >}}
```

## 参考

- [开发主题组件 | FixIt](https://fixit.lruihao.cn/contributing/components/)
- [如何开发 Hugo 主题组件 | FixIt](https://fixit.lruihao.cn/components/dev-component/)
