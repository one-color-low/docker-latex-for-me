# 説明
korosuke613様の
https://github.com/korosuke613/texlive-ja-devcontainer-template

を自分用にカスタマイズしたリポジトリです。

OS等の環境を問わず、いつでも同じLaTeX執筆環境を構築できます。

# 使用準備
1. PCにDockerとVSCode(+拡張機能のremote containerとLaTeX Workshop)を入れる(OSは問わない)
2. このリポジトリを`git clone` 
3. クローンしたフォルダをVSCodeで開く
4. 左下の「><」のようなアイコンをクリックし、`Remote-Containers: Reopen in Container`を選択
5. 右上の「▶」アイコンでsample.texをビルドできるようになる

# 推奨運用方法
このリポジトリは環境構築用リポジトリです。そのため、論文をGit管理した場合は3と4の間で以下の手順を入れてください。
- `rm -rf .git/`し、環境構築用リポジトリでは無くする
- 論文執筆用のリポジトリとして`git init`する