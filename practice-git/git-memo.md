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

 git commit -m "git-memo"

```

## gitの使い方　コミットまでの流れ

1. git statusやgit diffを使って変更を確認する
2. コミットしたいファイルをgit addを使ってステージング(選択)する
3. git commitでコミットする　この時、-m のあとにダブルクォーテーション（""）で囲ってコミットタイトルを指定する
4. git logでコミットできたか確認する ログが長い場合qを押すと戻れる

## gitの使い方　リモートリポジトリとのやり取り編

- git fetchでリモートリポジトリの最新の状態を取得する
- git pushで変更をリモートリポジトリに反映する
- git merge origin/branch-nameでリモートの変更を取り込む　**この時、現在のブランチを必ず確認し、間違えないようにする**
- git pullはまだ早いから使わない

## gitの使い方 ブランチの使い方編

1. githubのissueからリモートのブランチを作成　リモートリポジトリ使うときはローカルで作成しないのが吉
2. git fetchでリモートの情報を取得
3. git branch -aでブランチを確認
4. git checkoutでブランチを変更
5. プッシュしたらgithubに行ってプルリクエストを作成
6. マージされたらgit fetch --pruneとローカルでのマージ（やり方はリモートリポジトリのやり取り編を参照）
7. git branch -d で使い終わったブランチを削除

## gitの用語

ブランチ:　世界線の分岐のようなもの　変更がすべてに反映されないので安全
マージ: ブランチの内容をほかのブランチと統合する
HEAD: 現在のブランチを示す

githubの機能
issue: タスクとかを書ける　対応したブランチを発行できる
pull request: ソースコードの変更を見てもらい、リモートのブランチにマージする

## 勉強したコマンド一覧

**Caution**: <>で囲まれた部分は<>を書かず自分で内容を考えて書く

```bash
# 基本のコマンド（git以外）
ls # ディレクトリの中身の確認
ls -al # -aで隠しファイルも表示、-lで詳細表示　同時に指定できる
cd <dir_name> # R-booksディレクトリへの移動
pwd # 現在のディレクトリの確認
code . # vscodeを現在のディレクトリで起動
mv <arg1> <arg2> # 名前変更や移動ができる ややこしいので紹介程度

# gitコマンド　コミットまで
git status # 現在のブランチや変更状態の確認
git add <file> # ファイルをステージングする（コミットの対象に選ぶ）
git diff # ファイルの変更を確認する
git diff --staged # すでにステージングしたものを比較したいときはこっち
git log # コミット履歴を確認する
git commit -m "<コミットタイトル>" # ステージングしたファイルをコミット（セーブみたいなやつ）する　-m　はコミットタイトルを指定する

# gitコマンド　ブランチ関係
git branch # ブランチを確認
git branch -a # リモートブランチも確認する
git branch <branch-name> # 新しいブランチを作成
git branch -d <branch-name> # 指定したブランチを削除する　ローカルのみ
git checkout <branch-name> # HEADを変更
git checkout -b <branch-name> # 新規のブランチを作成し、現在のブランチの変更もする
git checkout -b <branch-name> <origin/branch-name> # リモートブランチと紐づいたブランチを作成しチェックアウト
git merge <branch-name> # 指定したブランチの変更をHEADに行う

# gitコマンド　リモートリポジトリ関係
git push # リモートリポジトリのブランチにコミットを送信
git push origin <branch-name> # リモートリポジトリのどのブランチにプッシュするか指定する
git push -u  origin <branch-name> # リモートリポジトリのどのブランチにプッシュするか指定し、それを次からgit pushのみで反映できるようにする
git push -u  origin HEAD # 上記で現在のブランチを指定したいときに便利な記法　こっちのほうが間違えにくい
git fetch origin # リモートリポジトリの変更を受信
git fetch origin --prune # ブランチの削除情報も受信

# ghコマンド
gh auth login # GitHub CLIでログインする
gh auth status # ログイン状況の確認
gh repo create # 新規リポジトリの作成
gh repo clone <repo-name> # リモートからリポジトリをクローン
```
