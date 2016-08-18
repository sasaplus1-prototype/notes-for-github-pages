# notes-for-github-pages

notes for [GitHub Pages](https://pages.github.com/)

## Links

Helps for GitHub Pages

- [GitHub Pages](https://pages.github.com/)
- [GitHub Pages Basics](https://help.github.com/categories/github-pages-basics/)
- [Customizing GitHub Pages](https://help.github.com/categories/customizing-github-pages/)
- [GitHub Pages Troubleshooting](https://help.github.com/categories/github-pages-troubleshooting/)

GitHub Pages dependencies

- [GitHub Pages Dependency versions](https://pages.github.com/versions/)
- [GitHub Pages Dependency versions / Programmatic access](https://pages.github.com/versions.json)

Static site generator

- [Jekyll](https://jekyllrb.com/)

Template engine

- [Liquid](https://shopify.github.io/liquid/)
- [Liquid reference](https://docs.shopify.com/themes/liquid)
- [Liquid repository](https://github.com/Shopify/liquid/)
- [Liquid wiki](https://github.com/Shopify/liquid/wiki)

Articles

- [Articles for GitHub Pages](https://github.com/blog/search?utf8=%E2%9C%93&q=github+pages)

## ページを公開する

ページを公開するまでの手順について。

1. GitHubでリポジトリを作成する
2. リポジトリにファイルをコミットする
3. GitHubのリポジトリに変更を送信する

[User, Organization, and Project Pages](https://help.github.com/articles/user-organization-and-project-pages/)

### GitHubでリポジトリを作成する

`http://username.github.io/`にページを作るか、`http://username.github.io/projectname/`にページを作るかによって作成するリポジトリの名前とファイルを配置するブランチの名前を変える必要がある。

`http://username.github.io/`にページを作る場合は`username.github.io`という名前でリポジトリを作成し、`master`ブランチにファイルを配置する必要がある。（以前は`username.github.io`ではなく`username.github.com`だった）

[New GitHub Pages domain: github.io](https://github.com/blog/1452-new-github-pages-domain-github-io)

これ以外にページを作る場合は`gh-pages`ブランチにファイルを配置する必要があったが、GitHubのアップデートにより必要がなくなった。また、`master`ブランチの`/docs`ディレクトリ以下に配置することも可能になった。

[Simpler GitHub Pages publishing](https://github.com/blog/2228-simpler-github-pages-publishing)

`http://username.github.io/projectname/`にページを作る場合は`projectname`という名前でリポジトリを作成し、`gh-pages`ブランチにファイルを配置する必要がある。（以前は`gh_pages`も許容されていたような記憶があるが、現在は不明）

[Configuring a publishing source for GitHub Pages](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/)

### リポジトリにファイルをコミットする

Gitを駆使してリポジトリにファイルをコミットする。

あるいはGitHubをブラウザで開いて[`New file`からファイルを追加](https://help.github.com/articles/creating-new-files/)したり、[`Edit`からファイルを編集する](https://help.github.com/articles/editing-files-in-your-repository/)などをしてブラウザからコミットを行っても良い。

### GitHubのリポジトリに変更を送信する

変更を

```sh
$ git push origin (master または gh-pages)
```

でGitHubのリポジトリに変更を送信すると公開される。ブラウザからファイルをコミットした場合は必要ない。

## 404ページを自作のページにしたい

`404.html`もしくは`404.md`をリポジトリのルートに配置する。

[Creating a custom 404 page for your GitHub Pages site](https://help.github.com/articles/creating-a-custom-404-page-for-your-github-pages-site/)

## コメント欄を付けたい

GitHub Pagesは静的なサイトを公開するためのものなので、コメント欄の機能はGitHub Pagesでは実現できない。

いくつかのGitHub Pagesで作成されたブログなどを見ると[DISQUS](https://disqus.com/)を使用してコメント欄としているユーザが多いように見える。

## サイトマップのXMLを自動生成させたい

`jekyll-sitemap`を使用する設定を指定することで自動生成されるようになる。`_config.yml`に以下を記述する。

```yaml
gems:
  - jekyll-sitemap
```

[Sitemaps for GitHub Pages](https://help.github.com/articles/sitemaps-for-github-pages/)

[jekyll/jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap)

## 独自ドメインを使いたい

リポジトリの一番上のディレクトリに`CNAME`という名前のファイルで使用したい独自ドメインを記述しておくと、そのリポジトリのGitHub Pagesへ記述された独自ドメインでアクセスすることができるようになる。

独自ドメインはAレコードに`192.30.252.153`と`192.30.252.154`を指定しておく。

[Using a custom domain with GitHub Pages](https://help.github.com/articles/using-a-custom-domain-with-github-pages/)

## SassとCoffeeScriptを使いたい

Sassはファイルの拡張子として`.scss`または`.sass`を付け、ファイルの先頭に`---`を2行続けて記述すると、Sassとしてコンパイルされる。

```scss
---
---
body {
  color: black;
}
```

コンパイルされたファイルは拡張子が`.css`に変更されたものになり、ファイルの配置場所は同じディレクトリとなる。

CoffeeScriptは`_.config.yml`に以下を記述する。

```yaml
gems:
  - jekyll-coffeescript
```

その上でSassと同様にファイルの拡張子として`.coffee`を付け、ファイルの先頭に`---`を2行続けて記述すると、CoffeeScriptとしてコンパイルされる。

```coffee
---
---
do -> console.log 'Hello!'
```

コンパイルされたファイルは拡張子が`.js`に変更されたものになり、ファイルの配置場所は同じディレクトリとなる。

[Assets](http://jekyllrb.com/docs/assets/)

## ローカルマシンにGitHub Pagesの環境を作りたい

[github-pages](https://rubygems.org/gems/github-pages)というgemが公開されているので、これをインストールすることでGitHub Pagesとほぼ同等の環境を作る事ができる。

[Cutting the GitHub Pages Gem](https://github.com/blog/1581-cutting-the-github-pages-gem)

## リポジトリのメタデータを使いたい

`{{ site.github }}`以下にリポジトリのメタデータがあらかじめ格納されている。

[Repository metadata and plugin support for GitHub Pages](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

[Repository metadata on GitHub Pages](https://help.github.com/articles/repository-metadata-on-github-pages/)

### リポジトリのメタデータをJavaScriptから使いたい

Jekyllの`jsonify`フィルタを使う事でJSON形式の文字列に変換できるので、これを`script`タグに直接埋め込むことで使用できる。

```html
<script type="application/json">{{ site.data | jsonify }}</script>
```

```html
<script>
window.site = {
  data: JSON.parse({{ site.data | jsonify }})
};
</script>
```

### リポジトリのメタデータをローカルマシンのGitHub Pagesの環境で使いたい

`jekyll-github-metadata`を使用する設定を指定することで使用可能になる。`_config.yml`に以下を記述する。

`_config.yml`に以下を記述する。

```yaml
gems:
  - jekyll-github-metadata
```

[Preview GitHub Pages metadata locally](https://github.com/blog/2154-preview-github-pages-metadata-locally)

[jekyll/github-metadata](https://github.com/jekyll/github-metadata)

## Jekyllを無効化したい

リポジトリの一番上のディレクトリに`.nojekyll`という名前のファイルを配置しておくと、Jekyllが無効化される。
