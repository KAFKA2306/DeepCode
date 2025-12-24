# ツール (Tools)

このディレクトリは、DeepCodeのエージェントが使用するMCP (Model Context Protocol) サーバーと、各種ユーティリティツールの実装を含みます。

## ディレクトリ構造

| ファイル名 | 説明 |
|:---|:---|
| `bocha_search_server.py` | Bocha検索エンジンのMCPサーバー実装。Web検索機能を提供します。 |
| `code_implementation_server.py` | コード生成、編集、テスト実行を行うコアサーバー。 |
| `code_indexer.py` | コードベースのインデックス作成を行い、RAG (Retrieval-Augmented Generation) を支援します。 |
| `code_reference_indexer.py` | 外部リポジトリやライブラリリファレンスのインデックス作成を行います。 |
| `command_executor.py` | システムコマンド（bash/shell）を安全に実行するためのMCPツール。 |
| `document_segmentation_server.py` | 大規模なドキュメント（論文など）を意味のあるチャンクに分割するサーバー。 |
| `git_command.py` | Git操作（クローン、コミットなど）を行うツール。 |
| `pdf_converter.py` | PDFファイルをテキストやMarkdownに変換するツール。 |
| `pdf_downloader.py` | URLからPDFをダウンロードして保存するツール。 |

## 役割

これらのツールは、エージェントが外界と作用するための機能モジュールです。MCP標準に準拠しており、オーケストレーターからのリクエストに応じて独立したプロセスとして機能、またはライブラリとして呼び出されます。

## 使用方法

通常、これらのスクリプトは直接実行されるのではなく、`mcp_agent.config.yaml` の設定に基づいてエージェントシステムによって自動的に初期化・管理されます。
特定の機能をデバッグする場合のみ、単体で実行・テストすることがあります。
