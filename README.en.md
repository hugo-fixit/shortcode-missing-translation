<!-- markdownlint-disable-file MD033 MD041 -->
<h1 align="center">shortcode-missing-translation | FixIt</h1>

<img width="810" alt="image" src="https://github.com/user-attachments/assets/a18d2888-0f5d-4c82-929e-c79b6465c04a" />
<img width="810" alt="image" src="https://github.com/user-attachments/assets/7868c724-8bbd-4336-b43d-4ed607019988" />

<div align="center" class="ignore">
  <p>Temporarily renders the translated content of the current page in the specified language when translation is missing.</p>
  <a href="/README.md">简体中文</a> |
  <a href="https://fixit.lruihao.cn/zh-cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=chinese_traditional">繁體中文</a> |
  English |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=french">Français</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=russian">Русский язык</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=spanish">Español</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=hindi">हिन्दी</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=deutsch">deutsch</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=korean">한국어</a> |
  <a href="https://fixit.lruihao.cn/ecosystem/hugo-fixit/shortcode-missing-translation/?lang=japanese">しろうと</a>
</div>

## Requirements

Applicable to all Hugo themes.

## Install Component

The installation method is the same as [installing a theme](https://fixit.lruihao.cn/documentation/installation/). There are several ways to install, choose one, Here are two mainstream ways.

### Install as Hugo Module

First make sure that your project itself is a [Hugo module](https://gohugo.io/hugo-modules/use-modules/#initialize-a-new-module).

Then add this theme component to your `hugo.toml` configuration file:

```toml
[module]
  [[module.imports]]
    path = "github.com/hugo-fixit/FixIt"
  [[module.imports]]
    path = "github.com/hugo-fixit/shortcode-missing-translation"
```

On the first start of Hugo it will download the required files.

To update to the latest version of the module run:

```bash
hugo mod get -u
hugo mod tidy
```

### Install as Git Submodule

Clone [FixIt](https://github.com/hugo-fixit/FixIt) and this git repository into your theme folder and add it as submodules of your website directory.

```bash
git submodule add https://github.com/hugo-fixit/FixIt.git themes/FixIt
git submodule add https://github.com/hugo-fixit/shortcode-missing-translation.git themes/shortcode-missing-translation
```

Next edit `hugo.toml` of your project and add this theme component to your themes:

```toml
theme = ["FixIt", "shortcode-missing-translation"]
```

## Configuration

```toml
[gitInfo]
  repo = "https://github.com/hugo-fixit/docs"
  branch = "main"
  # the content directory path relative to the root of the repository
  dir = "content"
```

## Use Shortcode

Here is an example of usage:

```markdown
{{< missing-translation >}}
```

> [!TIP]
> Please ensure that there is at least one language translation available. If there are multiple language translations, the first one will be selected by default.

Or, specify an existing translation language:

```markdown
{{< missing-translation "en" >}}
```

## References

- [Develop Theme Components | FixIt](https://fixit.lruihao.cn/contributing/components/)
- [How to Develop a Hugo Theme Component | FixIt](https://fixit.lruihao.cn/components/dev-component/)
