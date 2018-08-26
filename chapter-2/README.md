# Ansibleの基礎

## Ansibleのコンポーネント

- Module
  - Core : Ansibleの基本機能を構成するモジュール
  - Network : 代表的なネットワークベンダー機器をサポートするモジュール
  - Certified : RedHatにより認定されたベンダーが提供するモジュール
  - Community : コミュニティメンバによりメンテされていくモジュール
  - etc...
- Playbook : 一連の作業を順序立てて定義するファイル
- Inventory : ターゲットノードの接続情報を記載したファイル
- Plugins : core機能を拡張したり、追加機能を提供するコンポーネント
  - Connection
  - Lookup
    - lookup
    - with
  - Callback
  - Cache
  - Vars
  - Filters
- Python API
- Ansible CLI
  - ansible-doc
  - ansible-galaxy
  - ansible-pull
  - ansible-vault

## Ansible運用ユーザの作成

## SSH公開鍵認証の設定

```bash:SSH公開鍵認証の登録
$ ssh-keygen -t rsa
$ ssh-copy-id -o StrictHostChecking=no -i $HOME/.ssh/id_rds.pub <target_node|localhost>
```

## ansible.cfgの設定

1. 環境変数のファイルパス(ANSIBLE_CONFIG=/usr/local/ansible/conf/ansible.cfg)
2. カレントディレクトリ(./ansible.cfg)
3. ホームディレクトリ($HOME/.ansible.cfg)
4. /etc/ansible/ansible.cfg

## コラム

```bash:localでのansible-playbook実行
$ cat local-sample.yml
- hosts: localhost
  connection: local
  ...

$ ansible-playbook -i localhost, local-sample.yml
```
