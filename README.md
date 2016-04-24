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

`http://username.github.io/projectname/`にページを作る場合はリポジトリの名前は任意に、`gh-pages`ブランチにファイルを配置する必要がある。（以前は`gh_pages`も許容されていたような記憶があるが、現在は不明）

[New GitHub Pages domain: github.io](https://github.com/blog/1452-new-github-pages-domain-github-io)

### リポジトリにファイルをコミットする

Gitを駆使してリポジトリにファイルをコミットする。

あるいはGitHubをブラウザで開いて[`New file`からファイルを追加](https://help.github.com/articles/creating-new-files/)、[`Edit`からファイルを編集する](https://help.github.com/articles/editing-files-in-your-repository/)などをしてブラウザからコミットを行っても良い。

### GitHubのリポジトリに変更を送信する

変更を

```sh
$ git push origin (master または gh-pages)
```

でGitHubのリポジトリに変更を送信すると公開される。ブラウザからファイルをコミットした場合は必要ない。

## ローカルマシンにGitHub Pagesの環境を作りたい

[github-pages](https://rubygems.org/gems/github-pages)というgemが公開されているので、これをインストールすることでGitHub Pagesとほぼ同等の環境を作る事ができる。

[Cutting the GitHub Pages Gem](https://github.com/blog/1581-cutting-the-github-pages-gem)

## コメント欄を付けたい

GitHub Pagesは静的なサイトを公開するためのものなので、コメント欄の機能はGitHub Pagesでは実現できない。

いくつかのGitHub Pagesで作成されたブログなどを見ると[DISQUS](https://disqus.com/)を使用してコメント欄としているユーザが多いように見える。
