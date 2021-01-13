# 説明
korosuke613様の
https://github.com/korosuke613/texlive-ja-devcontainer-template

を自分用にカスタマイズしたリポジトリです。

OS等の環境を問わず、いつでも同じLaTeX執筆環境を構築できます。

# 使用準備
1. PCにDockerとVSCode(+拡張機能のremote container)を入れる(OSは問わない)
2. このリポジトリを`git clone` 
3. クローンしたフォルダをVSCodeで開く
4. 左下の「><」のようなアイコンをクリックし、`Remote-Containers: Reopen in Container`を選択
5. 右上の「▶」アイコンでsample.texをビルドできるようになる

# 推奨運用方法
このリポジトリは環境構築用リポジトリです。そのため、論文をGit管理した場合は以下の手順を入れてください。
- 3と4の間で`.git/`ディレクトリを削除し、環境構築用リポジトリでは無くする＆フォルダ名を変更する
- 4のあと、リモートのターミナルで論文執筆用のリポジトリとして`git init`する
- GitHubで新しいリポジトリを作っていつも通りpush
- 以降は新しいリポジトリの最新をクローンしてから`Remote-Containers: Reopen in Container`するか、``Remote-Containers: Attach to Running Container`してコンテナに入る
- commit操作は全てコンテナ内で行う

# 仕組み
- 準備の4をすると、このリポジトリの中のDockerfile等に従ってコンテナが作成される。
- そのコンテナにはLaTeXコンパイラが入っているのでコンパイル可能
- そのコンテナのworkdirにこのリポジトリがマウントされるので、作ったlatexファイルがコンテナ内にあるのと同じになる
- docker-compose.yamlでリモートのVSCodeにLaTeX Workshopが入れられるので、リモートのVSCodeで「▶」からコンパイルできる
- ~/.gitconfig:/root/.gitconfig によってホストのgitログイン情報とかがリモートに行ってくれる

# 用改善点
- LaTeX Workshopがなぜかdocker-compose時にインストールされない
- git管理はローカルのターミナルでやらないといけないのが不便