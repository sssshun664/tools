# YT Shuffle

複数の YouTube チャンネルから動画をランダム抽出してミックスし、公式 YouTube アプリ／サイトの `watch_videos` プレイリストとして開くスマホ向けツール。

## 機能

- **複数チャンネル対応**: 入力欄を必要なだけ追加して、それぞれから個別に動画を取得
- **2 段シャッフル**: 各チャンネルから「取得プール」内をシャッフルして N 本を抽出 → 全チャンネル分を再度シャッフルして 1 本のキューに
- **チャンネル指定**: `@handle` / `channel/UC...` / `user/...` / `c/...` / 素の `UC...` ID 形式に対応
- **保存済みチャンネルのショートカット**: 一度使ったチャンネルはチップとしてブラウザに残り、タップで再利用 / × で削除
- **直近の入力を復元**: 次回起動時に前回の入力欄を自動復元
- **プレイリスト URL 生成**: `youtube.com/watch_videos?video_ids=...` 形式で公式アプリにバトンを渡す
- **キュー操作**: 前 / 次 / 任意動画タップ / 再シャッフル
- **API キー保存**: `localStorage` にブラウザ内のみ保持

## 使い方

1. [Google Cloud Console](https://console.cloud.google.com/) で YouTube Data API v3 を有効化し API キーを取得
2. ツールを開いて API キーを入力
3. 「＋ チャンネルを追加」で必要な数だけチャンネル URL を入力（一度使ったチャンネルは下のチップから即追加可）
4. 「1ch あたり取得」(API から取ってくるプール) と「1ch あたり選出」(プールから無作為抽出する本数) を設定
5. 「シャッフル開始」をタップしてキューを生成
6. 「YouTube で開く」をタップすると公式 YouTube が開き、生成されたプレイリストを順次再生
   - YouTube Premium 加入者ならバックグラウンド再生・スリープ中再生が自動で適用されます

## 保存済みチャンネル

シャッフルが成功したチャンネルは自動的にローカルに保存され、次回以降はチップとして表示されます。

- **タップ**: 入力欄に追加（空欄があればそこに入り、無ければ新しい行が追加されます）
- **×**: 保存済みリストから削除
- **保存先**: `localStorage.yt_saved_channels`（ブラウザ内に閉じます）

## 入力形式

- `https://www.youtube.com/@channelname`
- `https://www.youtube.com/channel/UCxxxxxxxxxxxxxxxxxxxxxx`
- `https://www.youtube.com/user/legacyname`
- `https://www.youtube.com/c/customname`
- `@channelname`（素のハンドル）
- `UCxxxxxxxxxxxxxxxxxxxxxx`（24 文字のチャンネル ID）

## 技術仕様

- 単一 HTML ファイル（インライン CSS / JS、依存はフォント CDN のみ）
- YouTube Data API v3 の `channels` / `playlistItems` を使用
- LocalStorage キー
  - `yt_api_key` — API キー
  - `yt_last_channels` — 直近の入力欄
  - `yt_saved_channels` — ショートカットチップ用 `[{id, input, title, lastUsed}]`
- ダーク UI（`#0a0a0a` ベース、アクセント `#ff3d3d` → `#ff8c42`）
- レスポンシブ（モバイル最適化、最小タップ領域 44px 以上）

## 制限事項

- API キーが必須。クライアントサイドで利用するため、HTTP リファラ制限の付与を強く推奨
- `watch_videos` URL は YouTube 側の仕様で、長すぎる ID 列は途中で切られる可能性あり
- メンバーシップ限定動画やプレミアの予定動画は取得元の `uploads` プレイリストに含まれない場合あり
- API クォータ（既定で 10,000 ユニット/日）の制約を受ける
