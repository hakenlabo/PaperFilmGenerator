# ペーパーフィルムジェネレーター — 開発メモ

- 1ファイル構成（`index.html` に HTML/CSS/JS すべて）。外部ライブラリなし。
- 公開：GitHub `hakenlabo/PaperFilmGenerator` の main ルートを GitHub Pages で配信（`.nojekyll`）。
  https://hakenlabo.github.io/PaperFilmGenerator/
- 更新手順：`index.html` をブラウザ（file://）で確認 → コミット → `git push`（SSH）。数十秒で公開版に反映。
- 元ファイル：Google Drive `02_AREA/03 研究/Paper film/Paperfilm Generator/1_sheet_generator_0911.html`（2026-09-11版）。
  以後はこのリポジトリが正本。Drive 側の古い版（`1_sheet_generator_6.html` など）は編集しない。
- 関連：同フォルダの `PaperFilm_scan_to_video_0907.html`（スキャン → 動画）は別ツール。フィルム規格の実寸表（FORMATS）は両者で共通にする想定。
- 表示言語（2026-10-29〜）：日本語・英語・韓国語。画面の文字は `data-i18n` / `data-i18n-html` のキーで、
  スクリプト中の文字は `tr('キー', {値})` で出す。辞書は `I18N`（ja / en / ko）。文字を足すときは3言語とも書く。
  ローカル変数に `t` が多いので翻訳関数は `tr`。選んだ言語は localStorage `pfg:lang`、URL の `?lang=` が優先。
  PDF に入る文字（規格ラベル・コマ番号）は Helvetica なので ASCII のみ、言語に関係なく同じ。
- アプリ名は「ペーパーフィルムジェネレーター」（2026-10-29 に「作画用紙ジェネレーター」から改名）。
- `scan.html`：スキャン → 動画（2026-10-29 公開）。元は Drive の `PaperFilm_scan_to_video_0907.html`。日本語・英語・韓国語（ジェネレーターと同じ I18N・tr・保存キー `pfg:lang` なので、片方で選んだ言語がもう片方にも効く）。
  フィルム規格表（FORMATS）と layout() を index.html から書き写して持っている（共通化はまだ）。
  **規格表を直すときは index.html と scan.html の両方を直す**。トンボ検出は 0911 版の列ごとの小さい印があっても動くことを確認済み。
- 2つのページは見出しの横のリンクで行き来できる（index.html → scan.html、scan.html → ./）。
- フィルム規格表（2026-10-29 に SMPTE 原本と照合して修正）：出典は FORMATS 直前のコメント。
  幅は実寸（15.95 / 34.975 / 69.95）、35/70mm の送りは 0.1870 in（4.75 mm）の整数倍、画面位置は規格の許容範囲の中央。
  画面は送り幅の中で上下中央（layout の gapY）。index.html と scan.html の FORMATS・layout は同一に保つ（diff で確認）。
  フィルムメニューには画面比を表示（fmtRatio、4:3・16:9 に1%以内なら「≈」を添える）。
  両ページのヘルプの下に「わずかな誤差があり得る」注記（tolNote、3言語）。
- 版番号（2026-10-29 に v1.0）：両ページの `APP_VERSION` と見出し横の表示、`CHANGELOG.md`、git タグ `v1.0` 形式。
  版を上げるときはこの4つをそろえる。小さな修正は v1.0.1、機能追加は v1.1 のように上げる。
