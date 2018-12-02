# Note1
忘備録ってやつです。The note for me for avoiding to forget all.

## Github Desktopについて
<bold>Commit時に、"Cannot push these commits as they contain an email address marked as private on GitHub."とエラーが出る。</bold>

設定時のE-mailアドレスが、プライベートなものを設定している（そして、プライベートアドレスを利用したCommitをGitHubで禁止する設定にしている。）
File > Options > Git > e-mail　でEmailをGitHubがくれるやつ（usename.@users.noreply.github.com）に変更する。

<hr>
<bold>GitHubでStash（退避）したい。</bold>

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
<hr>

## 統計について
たまに論文で、PCA→クラスタ解析って流れを見る。
これの意図としては、互いに独立な主成分でクラスターを作ることで、それぞれのクラスターの性質をはっきりと示せるからなのではないかと考えている。
けど、それなら、ランダムフォレストなりに入れたほうが良いかもしれない。ランダムフォレストも、機械学習と考えると、たくさんのデータを入れたほうがいいような気もするし（これ誤解かな？）、難しそう。
<hr>



