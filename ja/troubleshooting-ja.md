# トラブルシューティング

## ConfluenceのURLを与えてもAtlassian MCPを使って読み取ろうとしてくれず読み取りに失敗する

### 記載日およびツールとバージョン

記載日：2025/12/29
ツールとバージョン：Gemini CLI, v0.22.4

### 事象

ConfluenceのURLを与えてもAtlassian MCPを使って読み取ろうとしてくれない。
Web fetchを使おうとして失敗する。

### 原因

ConfluenceのURLが短縮URLであること

### 解決策

ConfluenceのURLは短縮URLでないものを取得して渡すようにする
