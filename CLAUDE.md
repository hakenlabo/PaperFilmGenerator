# 作画用紙ジェネレーター — 開発メモ

- 1ファイル構成（`index.html` に HTML/CSS/JS すべて）。外部ライブラリなし。
- 公開：GitHub `t1912-hub/PaperFilmGenerator` の main ルートを GitHub Pages で配信（`.nojekyll`）。
  https://t1912-hub.github.io/PaperFilmGenerator/
- 更新手順：`index.html` をブラウザ（file://）で確認 → コミット → `git push`（SSH）。数十秒で公開版に反映。
- 元ファイル：Google Drive `02_AREA/03 研究/Paper film/Paperfilm Generator/1_sheet_generator_0911.html`（2026-09-11版）。
  以後はこのリポジトリが正本。Drive 側の古い版（`1_sheet_generator_6.html` など）は編集しない。
- 関連：同フォルダの `PaperFilm_scan_to_video_0907.html`（スキャン → 動画）は別ツール。フィルム規格の実寸表（FORMATS）は両者で共通にする想定。
