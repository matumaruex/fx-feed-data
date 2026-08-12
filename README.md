# FX feed data

Cloudflare Worker の公開FXフィードを15分ごとに取得し、GitHub ActionsでJSONとして保存する中継リポジトリです。

## ChatGPTから読むURL

- まとめて取得: `https://raw.githubusercontent.com/matumaruex/fx-feed-data/main/fx-data.json`
- USD/JPY: `https://raw.githubusercontent.com/matumaruex/fx-feed-data/main/data/usdjpy.json`
- EUR/USD: `https://raw.githubusercontent.com/matumaruex/fx-feed-data/main/data/eurusd.json`

`fx-data.json` には、生成時刻の `generated_at` と、両通貨の最新取得データが入ります。

## 更新方法

`.github/workflows/update-fx-data.yml` が15分ごとに自動実行されます。GitHubの **Actions → Update FX data → Run workflow** から手動更新もできます。

取得失敗やJSON形式の異常がある場合は既存データを上書きせず、ワークフローを失敗させます。
