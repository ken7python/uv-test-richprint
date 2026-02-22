## uv使ってみた

### uv学習ログ

#### インストール
``curl -LsSf https://astral.sh/uv/install.sh | sh`

#### プロジェクト作成・依存関係管理
```
uv init                 # 新規プロジェクト作成
uv add requests         # 依存関係を追加（pyproject.toml & lock更新）
uv remove requests      # 依存関係を削除
uv lock                 # lock（uv.lock）を生成/更新
uv sync                 # lockに合わせて環境へインストール（再現性重視）
uv tree                 # 依存関係ツリー表示
```

#### 実行系
```
uv run python -V        # プロジェクト環境でコマンド実行
uv run python main.py   # スクリプト実行
uv run -m pytest        # -m でモジュール実行もOK
```

#### エクスポート
```
uv export --format requirements.txt
uv export --format pylock.toml      # PEP 751
```

#### uv内のpip
```
uv pip install requests
uv pip uninstall requests
uv pip list
uv pip freeze
```

