# Every Door で菊名駅前のOSMを修正してみた

**FOSS4G Hiroshima / SotM Asia OSAKA 振り返りハッカソン 2026**
by chihana-0421 (FuruhashiLab)

## 成果物

🗺️ **Before/After 比較マップ**
https://furuhashilab.github.io/Hackathon_Oct_ChihanaUsui/

## 概要

FOSS4G Hiroshima / SotM Asia OSAKA 2026 で紹介された **Every Door** を使って、菊名駅（横浜市港北区）周辺のOpenStreetMapデータを現地確認しながら修正した。

OSMを確認したところ、菊名駅前の店舗情報が実態と大きく乖離していることに気づいた（閉店した店舗が残っている、`fixme`タグが多数）。Every Doorを使うことで、スマートフォンから直感的にPOIを編集できることを体験した。

## 使用技術

| 技術 | 用途 |
|------|------|
| [Every Door](https://every-door.app/) | スマートフォンからOSMのPOIを現地編集 |
| [OpenStreetMap](https://www.openstreetmap.org/) | ベースマップ・編集対象データ |
| [Overpass Turbo](https://overpass-turbo.eu/) | 編集前後のOSMデータをGeoJSONとして取得 |
| [Leaflet.js](https://leafletjs.com/) | Before/After比較Webマップの作成 |
| GitHub Pages | 成果物の公開 |
| Claude Code (Sonnet 4.6) | コーディング・GitHub操作の支援 |

## 編集内容（菊名駅から半径200m）

現地を歩いて確認し、以下の編集を行った。

- **削除**：建物ごと建て替わり跡形もない店舗を5〜10件削除
- **閉鎖**：建物は残っているが別テナントが入っている店舗を閉鎖マークに更新
- **新規追加**：OSMに未登録だった店舗・施設を約20件追加

## ファイル構成

```
├── index.html            # Before/After比較Webマップ
├── before_kikuna.geojson # 編集前のOSMデータ（Overpass取得）
├── after_kikuna.geojson  # 編集後のOSMデータ（Overpass取得）
├── LICENCE               # CC BY 4.0
└── README.md
```

## ライセンス

[Creative Commons Attribution 4.0 International (CC BY 4.0)](./LICENCE)

地図データ © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors (ODbL)
