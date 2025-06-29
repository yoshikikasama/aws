# Terraform

## setup

tfenv install

```txt
brew install tfenv
```

terraform can install list

```txt
tfenv list-remote
```

install

```txt
tfenv install <version>
```

- use

```txt
tfenv use <version>
terraform version
tfenv list
terraform init
```

### git-secrets

秘密鍵をコミットするのを防ぐ

```txt
brew install git-secrets
```

端末全体の git でバージョン管理されているリポジトリの保護

```txt
git secrets --install ~/.git-templates/git-secrets
git config --global init.templatedir '~/.git-templates/git-secrets'
git secrets --register-aws --global
cat ~/.gitconfig
```

[git-secrets の設定方法](https://qiita.com/tanamoru/items/c3ff02bf56750bf63afe)

## terraform command

- terraform plan : 実行計画を確認
- terraform apploy <-auto-approve>: 変更デプロイ。
- terraform destroy: リソース削除
- terraform console: 指定された設定で組み込み関数を試せる。
- terraform fmt: 整形

- HCL2

  - HashiCorp Language2
  - json に似ている。簡単なプログラムをかける。
  - "="で指定。
  - コメント書ける。

- local: local 固定変数。
- variable: 外部から変更可能な変数。
- データ型:

  - string
  - number
  - bool
  - object: key value
  - tuple: 配列の N 番目にどう言った型を使うか決められたデータ
  - list: 配列
  - map: キーが文字列、バリューが型となる配列
  - set: バリューの重複が排除される入れる

- 変数の上書き方法
  - 環境変数
    - 実行ログに残らない
  - 変数ファイル (terraform.tfvars)
    - git 管理できる
  - コマンド引数 (-var <変数名=value>)
    - 実行ログに残る。一時的な利用。

[gitignore.io](https://www.toptal.com/developers/gitignore/)
