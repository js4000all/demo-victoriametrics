# demo-victoriametrics

VictoriaMetricsとGrafanaのデモ環境

## 構成

- vmagent: メトリクスの収集と転送
- vmstorage: データの保存
- vminsert: データの挿入処理
- vmselect: クエリ処理
- grafana: 可視化

## 起動方法

```bash
docker compose up -d
```

## アクセス方法

- Grafana: http://localhost:43000
  - ユーザー名: admin
  - パスワード: admin

## データソースの設定

Grafanaにログイン後、以下の手順でVictoriaMetricsをデータソースとして追加してください：

1. 左メニューの「Configuration」→「Data sources」を選択
2. 「Add data source」をクリック
3. 「Prometheus」を選択
4. URLに `http://vmselect:8481/select/0/prometheus/` を入力
5. 「Save & Test」をクリック
