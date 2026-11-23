# RUIN

iOS 版 LINE 向けの非公式機能拡張（Tweak）です。  
既読回避、送信取消メッセージの保持、ミュート送信、季節・トークエフェクト、タブや表示のカスタマイズ、着せかえ・カスタムフォント適用などの機能を提供します。

> [!NOTE]
> 本プロジェクトは非公式の拡張機能であり、LINEヤフー株式会社およびその関連会社とは一切関係がありません。利用は自己責任でお願いします。

---

## 対応環境

| 項目 | 内容 |
| :--- | :--- |
| **対応 LINE バージョン** | **26.17.0**（Build `2026.1103.1841`）のみ |
| **対応 OS** | iOS 18.0 以降 |
| **アーキテクチャ** | `arm64` / `arm64e` |
| **利用可能な環境** | **LiveContainer** / **Sideload**（無料 Apple ID・有料購入証明書の両方に対応） / **Jailbreak**（Rootless・Rootful） |

### テスト済み実機

以下の実機環境で動作テストを行っています。

- **iPhone SE（第2世代）** — iOS 27 / LiveContainer / 有料証明書署名（ESign, GBox）
- **iPad（第8世代）** — iOS 18.2.1 / Dopamine（Rootless Jailbreak）

---

## スクリーンショット

| ホーム画面 | LINE 設定内の入口 | RUIN 設定 |
| :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/home.png" width="240" alt="Home Screen" /> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/settings-entry.png" width="240" alt="Settings Entry" /> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/ruin-settings.png" width="240" alt="RUIN Settings" /> |

| カスタムフォント | メッセージ長押しメニュー | ミュート送信 |
| :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/local-font.png" width="240" alt="Local Font" /> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/chat-menu.png" width="240" alt="Chat Menu" /> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/mute-send.png" width="240" alt="Mute Send" /> |

| このメッセージまで既読 | 既読者一覧 |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/mark-read-until.png" alt="このメッセージまで既読" width="320"> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/read-users.png" alt="既読者一覧" width="320"> |
| 長押しメニューから「このメッセージまで既読」を選択 | **自分以外が送信したメッセージ**でも、既読者と既読日時を確認できます。 |

| テーマ詳細 | iPadでのテーマ商品詳細 |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/theme-detail.png" alt="テーマ詳細" width="320"> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/ipad-theme-detail.png" alt="iPadでのテーマ商品詳細" width="320"> |
| テーマストアの商品詳細ページ | iPadで表示したテーマ商品詳細 |

| 季節・トークエフェクト（雪・積雪） | 青文字連動・バルーン再生 | 公式ハロウィン Lottie | スクロールプレビュー |
| :---: | :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/seasonal-snow.png" alt="季節・トークエフェクト（雪・積雪）" width="185"> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/seasonal-balloon.png" alt="青文字連動・バルーン再生" width="185"> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/seasonal-halloween.png" alt="公式ハロウィン Lottie" width="185"> | <img src="https://raw.githubusercontent.com/tqmane/ruin/main/docs/screenshots/scroll-preview.png" alt="スクロールプレビュー" width="185"> |
| 期間限定を解除した雪・積雪と青文字リンク | 青文字「誕生日」のタップ／送受信でのバルーン再生 | 公式キャッシュアセットによるハロウィン Lottie 再生 | `24h送信取消・ミュートメッセージ` 有効時の純正スクロールプレビュー |

---

## 機能一覧

### メッセージ・既読管理
- **既読を隠す**: トークを開いても既読をつけません。トーク一覧から個別の例外設定ができるほか、トーク画面ヘッダーのアイコンからも切り替えられます。
- **開いたトークの未読バッジを消す**: 「既読を隠す」がオンのとき、サーバー上の既読状態を変えずに端末上の未読バッジおよびトークタブの合計件数を消去します。
- **返信時に既読**: 自分が返信を送信したときだけ既読をつけます。
- **このメッセージまで既読**: メッセージ長押しメニューから、選択したメッセージまでを手動で既読にします（後続のメッセージは未読のまま保持）。
- **既読者一覧**: メッセージ長押しメニューの「既読者一覧」から、既読をつけたメンバーと日時を確認できます。アバター付きの専用シートで表示され、プロフィール情報はキャッシュして再表示を高速化しています。
- **送信取消の保持**: 相手が送信取消したメッセージ本文・受信済みメディアを端末内に保持し、「取消済」マーク付きで表示・プレビューできます。
- **24時間以内の送信取消**: 送信後 24 時間以内のメッセージ取消に対応します。
- **ミュート送信**: 送信ボタンを約 2 秒長押しするとメニューが開き、相手に通知を送らずに送信できます。
- **スタンプを GIF でコピー**: メッセージ長押しメニューからスタンプを GIF 画像としてコピーできます。
- **Flex JSON コピー（開発者向け）**: Flex メッセージの長押しメニューから、Flex の JSON をそのままコピーできます（設定の「開発者」カテゴリで有効化、既定は OFF）。

### 表示・ナビゲーション・誤操作防止
- **不要要素の非表示**: 広告、おすすめ欄、音声入力ボタン、Agent-i バーを個別に非表示化できます。
- **パネルの高さ・表示修正**: サブ端末モード等で正しく表示されない、またはレイアウトが崩れるスタンプパネルおよび ＋ パネルの高さと表示を補正します。
- **入力欄の拡張は最大 3 行まで**: 長文入力時も入力欄は 3 行までしか広がらず、それ以上は入力欄の内部でスクロールします。
- **プロフィールアイコンを左に配置**: ホーム画面のプロフィール表示レイアウトを左配置に切り替え、自身の MID も表示します。
- **プロフィール画像の保存**: プロフィール画像ビューア内の保存ボタンから、表示中のアイコン・背景画像を写真ライブラリへ保存できます。
- **ステータスメッセージの色調整**: 友だちリストで背景が暗く文字が読みにくい場合、ステータスメッセージの文字色を自動で明るくします。
- **以前のホーム画面を使う**: 以前のホーム画面レイアウトに切り替えます（再起動後に反映）。
- **季節・トークエフェクト**: LINE の表示条件（季節期間や「誕生日」「おめでとう」「シャボン玉」「雪」「桜」「紅葉」「七夕」「梅雨」「ハロウィン」などのキーワード）から**期間限定の制限を解除**して通年で反応させます。該当語句は LINE 標準と同様に**青文字リンク化**され、送受信・タップのいずれでも純正 Lottie／季節背景（雪＋下部積雪・桜・紅葉・流星・雨・ハロウィン）を再生します。設定の「表示の管理」から季節外プレビューの常時表示も可能です。
- **スクロールプレビュー**: 「24h送信取消・ミュートメッセージ」を有効にしている環境でも、トーク一覧やアプリアイコン長押しの純正スクロールプレビューを利用できます。
- **タブ管理**: ショッピング、VOOM、ウォレット、ニュース・通話、設定、アプリなどのタブを非表示にできます。起動時に開くタブの固定にも対応しています（変更は再起動後に反映）。「タブを管理」ページでは非表示／復帰に加えてドラッグで並び替えができ、順序は ID ベースで保存され再起動後も保持されます（ホーム・トーク・設定は非表示不可）。
- **ローカル表示名変更**: トーク画面や設定から、この端末内だけの表示名に変更できます（相手には反映されず、いつでも元に戻せます）。
- **操作確認アラート**: グループ送信前（最低人数指定可）、通話開始前、カメラオン前、通話終了前に確認ダイアログを表示できます。
- **設定のカテゴリ分類**: バージョン情報を含む 13 セクションをルート画面に一覧表示し、タップで詳細ページへ進む 2 階層構成です（各行に Tabler アイコン付き）。
- **設定の検索**: ルート画面の検索バーで全カテゴリの設定を横断検索し、結果からその場で切り替えられます。

### テーマ・カスタムフォント
- **着せかえ機能**: ストア URL や商品 ID・バージョン指定での着せかえダウンロード、プレビュー、マイ着せかえへの追加が行えます。公式ショップ・スタンプショップへの導線も備えています。
- **テーマ詳細と公式ショップ連携**: 保存済みテーマをパッケージ形式でプレビュー表示でき、詳細画面から公式テーマショップの商品ページを LINE 内で開けます（プレビューにはショップのサムネイルを使用）。
- **テーマのチャット背景適用**: iPhone サイズの画面では、適用中テーマの背景画像もトーク背景に反映します。
- **カスタムフォント**: 32MB 以下の `.otf` / `.ttf` ファイルを読み込み、LINE 上のフォントを変更できます（いつでも標準に戻せます）。
- **ローカル LYP 機能**: アプリアイコン変更やトーク長押しメニュー等のローカル LYP UI 機能を有効化できます。

### その他
- **初期セットアップ**: 初回起動時に主要設定をまとめて行えるセットアップ画面を表示します（設定画面の「セットアップを開始」からも再表示可能）。
- **ユーザー検索・MID コピー**: MID を指定してプロフィールを開いたり、トーク画面ヘッダー長押しから MID をコピーしたりできます。トーク一覧やホームの友だち・グループ一覧の長押しメニューからも、MID / GID をコピーできます。
- **サブ端末ログイン切替**: ウェルカム画面／サブ端末ログイン画面に追加される切替ボタン（または「ログイン」長押し）および初期セットアップ画面から「通常の iPhone」と「サブ端末」モードを切り替えられます（ログイン後は設定のロックにより変更できません）。
- **年齢確認のスキップ**: 年齢確認ダイアログをスキップします。
- **新着メッセージのローカル通知**: アプリ起動中の 1対1・グループトークの新着メッセージをローカル通知で知らせます（※アプリ停止中のプッシュ通知には対応していません）。
- **診断・起動プロファイラ・UI 抽出**: ランタイムおよび機能対応状況の診断表示、次回起動時の起動計測ログの記録・閲覧・JSON エクスポート、画面 UI 構造の抽出・共有を行えます。
- **開発者モード**: 設定のバージョンバナーを 5 回タップすると解放される開発者向けゲートです。OFF の間は開発者カテゴリが一覧・検索から隠れ、診断も一部だけになります。以下の開発者向け機能はこのモードが前提です。
- **エフェクトメタ取得・エフェクト調査**: 純正と同じ経路で `getChatEffectMetaList` を 1 回実行して配布中のエフェクト定義を確認し、端末内のエフェクト設定やバンドル状態を JSON で出力できます（開発者向け）。
- **多言語対応**: 日本語・英語・韓国語・簡体字中国語・繁体字中国語の 5 言語に対応しています。

各機能の実現方法と詳細は [docs/features/](https://github.com/tqmane/ruin/blob/main/docs/features/README.md) を参照してください。純正チャットエフェクトの調査記録は [docs/chat-effect-investigation.md](https://github.com/tqmane/ruin/blob/main/docs/chat-effect-investigation.md) にあります。

---

## 導入方法

### 設定画面の開き方
LINE の **「設定」タブ最下部** に追加される **「RUIN」** から開けます（iPad やサブ端末モード時は、ホーム画面右上の歯車アイコンからも開けます）。

### Jailbreak 環境（Rootless / Rootful）
リリースページにある環境別の `.deb` パッケージをインストールし、LINE を再起動してください。
- **Rootless**（Dopamine など）: `RUIN-<version>-rootless.deb`
- **Rootful**: `RUIN-<version>-rootful.deb`

> [!NOTE]
> Cydia Substrate や libhooker などの外部フックライブラリへの動的リンクは不要で、各環境の注入ローダーからそのまま読み込めます。

### LiveContainer（単体 dylib）
1. リリースページから `RUIN-<version>-LiveContainer.dylib` をダウンロードし、未改変（RUIN 未注入）の LINE iOS **26.17.0** 復号済み IPA を用意します（RUIN 注入済み IPA には二重注入しないでください）。
   - 5言語の翻訳・設定情報・アイコンがバイナリ内に同梱されているため、外部の `RUINResources.bundle` は不要です（従来の外部バンドル併用も引き続き対応しています）。
2. LiveContainer に LINE を導入し、標準の TweakLoader（Tweak 管理機能）から `RUIN-<version>-LiveContainer.dylib` を選択して LINE 向けに有効化します。

> [!NOTE]
> LiveContainer は dylib インポート時に既存チェックなしで `@executable_path/../../Tweaks` と `@loader_path` の `LC_RPATH` を追加するため、一度インポート済みのファイルを別フォルダ等へ再インポートすると起動時に `dlopen` が `duplicate LC_RPATH` で失敗します。必ず配布元またはビルド直後の未使用の `RUIN-<version>-LiveContainer.dylib` を 1 回だけインポートしてください。すでに重複した dylib を復旧する場合は macOS 上で `python3 tools/prepare_livecontainer.py <元のdylib> <出力dylib>` を実行して修復用コピーを作成できます。

### Sideload（IPA 注入・非脱獄）
1. 未改変（RUIN 未注入）の LINE iOS **26.17.0** 復号済み IPA と、リリースページの `RUIN-<version>-jailed.deb` を用意します（RUIN 注入済み IPA には二重注入しないでください）。
   - `jailed.deb` 内では `/Library/MobileSubstrate/DynamicLibraries/` 配下に `RUIN.dylib` と `RUINResources.bundle` が格納されています。
2. **ESign** / **GBox** などの署名ツール、または既存の `package.py` による個人署名フローで `RUIN.dylib` と `RUINResources.bundle` の両方をアプリへ注入・署名してインストールします。
   - 無料の Apple ID でも有料の購入証明書でも利用できます。

> [!TIP]
> 既存のトーク履歴やログイン状態を保持してアップデートする場合は、これまでと同じ Bundle ID と署名環境を引き継いでください。

---

## ビルド方法

### 必要な環境
- macOS / Xcode（iOS SDK を含む）
- `make`, `perl`, `python3`（ホストテストも実行する場合は `node`）

### コマンド

```bash
# Universal dylib (arm64 + arm64e) とツールをビルド -> build/RUIN.dylib
make -j4 all

# 配布用パッケージ (.deb 3種・LC用dylib・SHA256SUMS) を生成 -> dist/
make dist

# ホストテストの実行（任意）
make -j4 check-host
```

ビルド成果物は以下に生成されます。
- **バイナリ**: `build/RUIN.dylib`（手動注入時は `resources/RUINResources.bundle` も同梱してください）
- **配布パッケージ**: `dist/RUIN-<version>-{rootless,rootful,jailed}.deb`、`dist/RUIN-<version>-LiveContainer.dylib`、`dist/SHA256SUMS`

### 署名済み IPA の生成（開発者向け）
手元の `.ipa`・証明書（`.p12`）・プロファイル（`.mobileprovision`）を使って署名済み IPA を直接ビルドするスクリプトも同梱しています。

```bash
python3 tools/package.py \
  --ipa <LINE.ipa> \
  --profile <profile.mobileprovision> \
  --p12 <certificate.p12> \
  --password-file <password.txt> \
  --udid <device-udid>
```
