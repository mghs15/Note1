# Note1
忘備録ってやつです。The note for me for avoiding to forget all.

# Github Desktopについて
##Commit時に、"Cannot push these commits as they contain an email address marked as private on GitHub."とエラーが出る。

設定時のE-mailアドレスが、プライベートなものをしている（そして、プライベートアドレスを利用したCommitをGitHubで禁止する設定にしている。）
File > Options > Git > e-mail　でEmailをGitHubがくれるやつ（usename.@users.noreply.github.com）に変更する。

##GitHubでStashしたい。

Repository > Open in Command Promptで　
```console
git stash
```
と打てばよい。


