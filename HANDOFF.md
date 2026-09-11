# HANDOFF

## 目的

MacWhisper日本語説明書サイトを、既存の構成とデザインを活用しながらMacWhisper 14.8.1（1481）の内容へ更新する。

## 現在の状態

- `main` ブランチで更新作業を実施。
- GitHub Pagesへの公開と公開後の表示確認まで完了。
- 14.8.1の更新情報を独立した章としてページ先頭へ追加。
- 既存の実機画像39点は13.21.4時点のものとして明記。
- MacWhisper公式ヘルプの画像1点を出典表示付きで追加。

## データの場所（最初にここを確認）

- 公開サイト: <https://oharu-ai.github.io/macwhisper-help/>
- GitHubリポジトリ: <https://github.com/Oharu-AI/macwhisper-help>
- ローカルのリポジトリ: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/site`
- 引き継ぎファイル: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/site/HANDOFF.md`
- 公開トップページの原稿: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/site/index.html`
- 同内容の別入口: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/site/macwhisper-guide.html`
- 画像フォルダ: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/site/screenshots`
- 今回追加した公式画像: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/site/screenshots/official_cloud_model_picker.png`
- 今回の調査記録: `/Users/oharu/.codex/.chatgpt-projects/g-p-6a2aa12454348191afeb4d161224f99b/research/macwhisper-14-8-1-update`
- 公式画像の掲載元: <https://docs.macwhisper.com/article/18-cloud-transcription>
- 公式リリースノート: <https://macwhisper-site.vercel.app/release_notes.html>
- Gemini音声文字変換の公式資料: <https://ai.google.dev/gemini-api/docs/transcribe?hl=ja>

`sources/` はChatGPTプロジェクトから同期される読み取り専用資料であり、このサイト本体ではない。サイト更新は必ず上記 `site/` リポジトリで行う。

## 次回再開時の手順

1. この `HANDOFF.md` を読む。
2. 作業場所を上記 `site` フォルダにする。
3. `git status --short` と `git log -1 --oneline` で状態を確認する。
4. 公開サイトと公式リリースノートを比較する。
5. `index.html` を編集し、同じ内容を `macwhisper-guide.html` に反映する。
6. 画像参照とブラウザ表示を確認してから、`main` へ送信する。

## 変更内容

- 14.8.1で追加されたGemini 3.5 Transcribeを解説。
- 日本語対応、話者区別、単語タイムスタンプ、複数言語の自動判定を説明。
- クラウド処理時のプライバシー上の注意を追加。
- 14.8のディクテーション音声書き出し、モデル準備、安定性改善を追記。
- 14系Editor Viewの直接編集、話者整理、お気に入り、性能改善を追記。
- Cloud Models章を14.8.1の実機で確認した18接続先へ更新。
- About章とフッターを14.8.1（1481）、2026年9月更新へ変更。

## 主要ファイル

- `index.html`: GitHub Pagesのトップページ。
- `macwhisper-guide.html`: `index.html` と同一内容の別入口。
- `screenshots/official_cloud_model_picker.png`: MacWhisper公式ヘルプから引用した画面例。

## 確認結果

- `index.html` と `macwhisper-guide.html` の内容が一致。
- HTMLから参照する画像40点がすべて存在。
- ブラウザで全40画像の読み込み成功を確認。
- ブラウザで23章、重複IDなしを確認。
- デスクトップ表示（1280×720）を目視確認。
- `git diff --check` で空白エラーなし。

## 未解決事項

- 既存の実機画像は13.21.4のため、新版と配置が異なる箇所がある。誤認防止の注記は追加済み。
- MacWhisper公式リリースノートはGeminiの対応を76言語、現在のGoogle公式資料は85以上の言語と地域と表記している。説明書内に差異を明記済み。

## 次の作業

- MacWhisperの次回更新時に、公式リリースノートと実機のAbout画面を再確認する。
- 新しい公式スクリーンショットが公開された場合は、旧版画像を差し替える。

## 確認用コマンド

```sh
git status --short
git diff --check
python3 -m http.server 4173
```
