# Ansibleの基礎

## Ansibleのコンポーネント

- Module
  - Core : Ansibleの基本機能を構成するモジュール
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

## コラム

```bash:localでのansible-playbook実行
$ cat local-sample.yml
- hosts: localhost
  connection: local
  ...

$ ansible-playbook -i localhost, local-sample.yml
```
