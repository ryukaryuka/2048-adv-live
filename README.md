# 2048-adv-live

2048パーティーのADVレビューモード用の差し替えデータ（台詞・演出のJSONだけ）。
アプリ（デバッグ版・TestFlight）のレビューモードの「更新」で、`manifest.json` と照合して取り込まれる。
中身は本体リポジトリの `tools/adv_live_publish.py` で作る。スクリプトや画像は置かない。

## live/（本番のデータ配信）

- `live/beta/`：TestFlight・デバッグ版が見る。`live/prod/`：公開版が見る。
- `manifest.json` は署名つき（`manifest.sig`）。アプリは中の公開鍵で確かめ、合わないものは使わない。
- 書き出しは本体の `tools/live_publish.gd`（使い方は本体の `docs/live-ops.md`）。手で中身を書き換えると署名が合わなくなり、アプリは受け取らない。
