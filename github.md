# Github Desktopについて
## メール設定
Commit時に、"Cannot push these commits as they contain an email address marked as private on GitHub."とエラーが出る。

設定時のE-mailアドレスが、プライベートなものを設定している（そして、プライベートアドレスを利用したCommitをGitHubで禁止する設定にしている。）
File > Options > Git > e-mail　でEmailをGitHubがくれるやつ（usename.@users.noreply.github.com）に変更する。

## GitHubでStash（退避）したい。

Repository > Open in Command Promptで以下のコマンドを打てばよい。
```console
git stash
```
退避のリストは以下のコマンドから見られる。
```console
git stash show
```
削除するには、
```console
git stash drop
```
## gh-pagesのbuildエラー

`.nojekyll`ファイル（中身は空でよい）をgh-pagesのルートにおいてあげると解決するみたい。

https://github.blog/2009-12-29-bypassing-jekyll-on-github-pages/

<hr>
