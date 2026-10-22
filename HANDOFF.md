# 日本語UI試作版v5 操作ガイド追記（2026-10-12）

この節が現在の最新状態。下の15.4記事は従来ガイドの履歴。

- 目的: 既存の説明書サイトを、MacWhisper 15.5（1550）を元にした非公式日本語UI試作版v5に対応させる。
- 主要ファイル: `japanese-ui-v5.html`（13章の日本語操作ガイド）、`screenshots/ja-v5/`（実機画像19点）。`index.html` と `macwhisper-guide.html` には新ガイドへの案内を追加し、旧版基準を明示。
- 正規版との違い、同一アプリ識別子による設定/履歴共有、残る英語、表示名10+2件、キーチェーンの経緯、未検証範囲を掲載。重要な録音は正規版を使う案内。
- 全19画像は当日のv5実画面。ホームは履歴部分を切り取り、監視先/自動書き出し先の実パスを含む画面は非掲載。ライセンス/APIキーは掲載しない。
- アプリ本体・翻訳ZIP・個人保存場所は新ページへ追加していない。設定/権限/録音/文字起こし/送信を変更・実行していない。
- 公式ヘルプを読み、古い対応モデル/会議説明は15系公式更新履歴と実機を区別。調査記録はプロジェクトの `research/macwhisper-ja-v5-guide/`。
- 検証済み: 3 HTMLの画像参照・内部リンク・ID重複のエラー0。新ガイド19画像参照。空白エラーなし。ブラウザで1280px/390pxの表示、検索・空結果・説明開閉、代表画像の読み込みを確認。390pxでページ全体の横はみ出しなし。
- 公開済み: https://oharu-ai.github.io/macwhisper-help/japanese-ui-v5.html 。本文/画像のコミット `c067274`、Pages実行 https://github.com/Oharu-AI/macwhisper-help/actions/runs/38261954888 は成功。公開ブラウザで13章・19画像・非公式版の明記を確認。ブラウザ警告/エラー0。
- 未解決: v5での録音/文字起こし/外部送信の動作試験、全画面/全警告の確認は未実施。ページで未確認と明示。
- 次回: 公式更新と実機の版を確認。新ガイドと19画像を基準に更新し、従来の英語版画像と混同しない。認証や重要な録音に関わる検証は目的を決めて実施する。
- 確認コマンド: `git status --short`、`git diff --check`、`python3 -m http.server 4173 --bind 127.0.0.1`、`gh run list --limit 3`。

---

# HANDOFF

## 最初に読む結論

MacWhisper日本語説明書サイトは、2026年10月9日時点の最新版MacWhisper 15.4（1540）へ更新し、GitHub Pagesへ公開済み。

2時間程度の日本語音声をAPI課金なしで話者認識する場合の第一候補は、ローカルの「Qwen3-ASR 1.7B＋Nemotron」。比較候補は「Large v3 Turbo＋Nemotron」。冒頭10分を両方で試し、固有名詞と話者分離が良い方を本番に使う。

## 目的

既存の構成とデザインを活用しながら、MacWhisper日本語説明書を最新版の公式情報と実機表示に合わせる。次回作業者が「サイト本体・調査記録・画像の場所」を探さず再開できる状態にする。

## 現在の状態

- `main` ブランチへMacWhisper 15.4対応を送信済み。
- GitHub Pagesのビルド・公開は成功。公開サイトでも15.4（1540）の表示を確認済み。
- MacWhisper 15.4実機から個人情報を含まない設定画面4点を撮影して掲載。
- 既存の実機画像39点は13.21.4時点であることをページ下部に明記。
- API課金を行わない運用方針と、契約中のGemini・ChatGPT・Claude等を手動で後処理に使う方法を掲載。

## データの場所（最初にここを確認）

- 公開サイト: <https://oharu-ai.github.io/macwhisper-help/>
- GitHubリポジトリ: <https://github.com/Oharu-AI/macwhisper-help>
- ローカルのリポジトリ: `<project-root>/site`
- この引き継ぎファイル: `<project-root>/site/HANDOFF.md`
- 公開トップページの原稿: `<project-root>/site/index.html`
- 同内容の別入口: `<project-root>/site/macwhisper-guide.html`
- サイト画像: `<project-root>/site/screenshots`
- 今回の調査記録: `<project-root>/research/macwhisper-latest-2026-10-09`
- 旧14.8.1調査記録: `<project-root>/research/macwhisper-14-8-1-update`

`sources/` はChatGPTプロジェクトから同期される読み取り専用資料であり、サイト本体ではない。サイト更新は必ず上記 `site/` リポジトリで行う。

## 今回追加した実機画像

- `screenshots/v15_local_models.png`: Local Models。Qwen3-ASR 1.7B、Speaker Recognition表示を確認できる。
- `screenshots/v15_record_meetings.png`: Record Meetings。ライブ会議文字起こしと権限設定を確認できる。
- `screenshots/v15_cloud_models.png`: Cloud Models。15.4実機の18接続先を確認できる。
- `screenshots/v15_about.png`: About。15.4（1540）と最新版表示を確認できる。
- `screenshots/official_cloud_model_picker.png`: 以前追加したMacWhisper公式ヘルプの旧画面例。ページ内で旧版と明記。

ホーム画面には家族関係の文字起こし履歴が表示されていたため、15.4のホーム画像は撮影・掲載していない。

## 変更内容

- ヘッダー、更新章、About、フッターを15.4（1540）・2026年10月へ更新。
- 15.0.1〜15.4の主要変更を更新履歴へ追加。
- macOS 15以降が必要で、macOS 14は14.8.1が最終版であることを明記。
- フォルダ・サブフォルダ、ライブ会議文字起こし、CoreAudio権限、容量不足時の安全停止を追記。
- Qwen3-ASR、Nemotron/Pyannote、最大8話者をローカルモデル章へ追記。
- 2時間の日本語・話者認識ではQwen3-ASR 1.7B＋Nemotronを第一候補として案内。
- 日本語特化モデルは15.4実機でSpeaker Recognition表示がないため、複数話者用途の第一候補にしないと明記。
- Cloud Modelsを15.4実機の18接続先へ更新し、SpaceXAIのGrok Voice Transcribe 2を追記。
- Gemini 3.5 Transcribeは話者認識時に1ファイル30分までというGoogle公式制限を追記。
- 一般向けのGemini・ChatGPT・Claude等の月額契約とAPI契約は別であることを明記。
- API課金なしではローカル文字起こしを使い、完成テキストを契約中のAIアプリへ手動で渡して要約等に使う方針を追記。

## 公式情報

- 更新フィード: <https://macwhisper-site.vercel.app/appcast.xml>
- リリースノート: <https://macwhisper-site.vercel.app/release_notes.html>
- MacWhisper公式ヘルプ: <https://docs.macwhisper.com/>
- AI Providers: <https://docs.macwhisper.com/article/58-setting-up-ai-providers-in-macwhisper>
- 話者認識: <https://docs.macwhisper.com/article/32-automatic-speaker-recognition-in-macwhisper>
- Argmaxモデル管理: <https://app.argmaxinc.com/docs/guides/managing-models>
- Gemini 3.5 Transcribe: <https://ai.google.dev/gemini-api/docs/models/gemini-3.5-transcribe?hl=ja>

公式ヘルプの一部は15.4より古い。最新機能について矛盾する場合は、公式更新フィード、公式リリースノート、15.4実機表示を優先する。

## 確認結果

- `index.html` と `macwhisper-guide.html` は同一内容。
- HTMLは23章、参照画像40点、欠落画像0点、重複ID 0件。
- ローカルブラウザで画像40点の読み込み成功、警告・コンソールエラー0件。
- 公開サイトでも15.4（1540）、23章、画像40点、欠落画像0点を確認。
- `git diff --check` で空白エラーなし。
- 公開した本文・画像のコミット: `cd8b6e9`（Update Japanese guide for MacWhisper 15.4）。
- GitHub Pages公開処理: <https://github.com/Oharu-AI/macwhisper-help/actions/runs/37886147759>（success）。

## 未解決事項

- 既存画像39点は13.21.4のため、15.4と配置が異なる画面が残る。誤認防止の注記は掲載済み。
- MacWhisper公式ヘルプの会議録音、話者認識、クラウド接続先の記事は15.4より古い内容を含む。
- Qwen3-ASRとLarge v3 Turboの日本語精度は音質・話者・固有名詞で変わる。日本語の同一音源を用いた公式直接比較は確認できていないため、10分テストを推奨している。

## 次回再開時の手順

1. この `HANDOFF.md` を読む。
2. `cd <project-root>/site` を実行する。
3. `git status --short` と `git log -1 --oneline` で状態を確認する。
4. 公開サイト、公式更新フィード、公式リリースノート、実機Aboutを比較する。
5. `index.html` を編集し、同内容を `macwhisper-guide.html` に反映する。
6. 個人情報を含まない画面だけを撮影し、`screenshots/` に保存する。
7. 画像参照・章数・重複ID・ブラウザ表示を確認する。
8. `main` へ送信し、GitHub Pages成功後に公開サイトで再確認する。
9. この `HANDOFF.md` を確認済みの状態へ更新する。

## 確認用コマンド

```sh
git status --short
git log -1 --oneline
git diff --check
cmp -s index.html macwhisper-guide.html
python3 -m http.server 4173
gh run list --limit 5
```
# 2026-10-22 公式変更点の照合・修正

- 公式ヘルプ https://docs.macwhisper.com/ と公式リリースノート https://macwhisper-site.vercel.app/release_notes.html を確認。後者の先頭は15.7.1。公式更新フィードはWeb取得失敗のため、配信対象や公開日時までは断定しない。
- index.html/macwhisper-guide.htmlに15.5〜15.7.1の差分を追記。15.6正式日本語UI、会議自動停止、Qwen進捗、M1再試行、15.7.1のNeural Engineへ戻す変更と設定非表示、カメラ対処、音声読み込み修正を記載。旧画像は流用し撮影版を現行版と偽らない。
- japanese-ui-v5.htmlの先頭説明を履歴資料へ変更し、試作起動手順を現行手順として使わないよう警告。試作翻訳の公式採用は未確認と明記。
- 保存場所はこのsiteフォルダ、公開先は既存GitHub Pages。アプリ/録音/設定は今回変更なし。
- 本文コミット213a9bcをmainへ送信。Pages run 39711294341。index/macwhisper-guideの一致を確認。今回ブラウザ描画検証は未実施。差分検査でHANDOFF末尾空行の警告が出たため、この追記で修正。
- Pages run 39711294341 success、公開HTMLに正式日本語対応と15.7.1更新案内が反映されたことをcurlで確認。3ページの重複ID/内部アンカー/画像実在検査成功（40/40/19画像）。最終git diff --check成功。
