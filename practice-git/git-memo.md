# git簡易まとめ

やったこと

```bash
cd ./R-books # ディレクトリを移動
git branch #ブランチ
* main
  practice/git
git checkout practice/git
Switched to branch 'practice/git'
Your branch is up to date with 'origin/practice/git'.
git branch
  main
* practice/git
code . 

git add .\practice-git\git-memo.md
PS C:\Users\tkrly\R-books> git status
On branch practice/git
Your branch is up to date with 'origin/practice/git'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   practice-git/git-memo.md

```

gitの用語
ブランチ:　世界線の分岐のようなもの　変更がすべてに反映されないので安全
マージ: ブランチの内容をほかのブランチと統合する
HEAD: 現在のブランチを示す

githubの機能
issue: タスクとかを書ける　対応したブランチを発行できる
pull request: ソースコードの変更を見てもらい、リモートのブランチにマージする

```bash
# 基本のコマンド（git以外）
ls # ディレクトリの中身の確認
ls -al # -aで隠しファイルも表示、-lで詳細表示　同時に指定できる
cd R-books # R-booksディレクトリへの移動
pwd # 現在のディレクトリの確認
code . # vscodeを現在のディレクトリで起動
mv arg1 arg2 # 名前変更や移動ができる ややこしいので紹介程度

# gitコマンド　コミットまで
git status # 現在のブランチや変更状態の確認
git add file # ファイルをステージングする（コミットの対象に選ぶ）
git diff # ファイルの変更を確認する
git diff --staged # すでにステージングしたものを比較したいときはこっち
git log # コミット履歴を確認する
git commit -m "コミットタイトル" # ステージングしたファイルをコミット（セーブみたいなやつ）する　-m　はコミットタイトルを指定する

# gitコマンド　ブランチ関係
git branch # ブランチを確認
git branch -a # リモートブランチも確認する
git branch branch-name # 新しいブランチを作成
git branch -d branch-name # 指定したブランチを削除する　ローカルのみ
git checkout branch-name # HEADを変更
git checkout -b branch-name # 新規のブランチを作成し、現在のブランチの変更もする
git merge branch-name # 指定したブランチの変更をHEADに行う

# gitコマンド　リモートリポジトリ関係
git push # リモートリポジトリのブランチにコミットを送信
git fetch origin # リモートリポジトリの変更を受信
git fetch origin --prune # ブランチの削除情報も受信

# ghコマンド
gh auth login # GitHub CLIでログインする
gh auth status # ログイン状況の確認
gh repo create # 新規リポジトリの作成
gh repo clone 9R0M/KANO-C # リモートからリポジトリをクローン
```
