# YT Shuffle

YouTube チャンネルの動画をランダムにシャッフルして、公式 YouTube アプリ／サイトの `watch_videos` プレイリストとして開くスマホ向けツール。

## 機能

- **チャンネル指定**: `@handle` / `channel/UC...` / 素の `UC...` ID 形式に対応
- **動画取得**: YouTube Data API v3 の `playlistItems` を使ってアップロード一覧から最大 200 件まで取得
- **シャッフルキュー**: Fisher–Yates で並べ替え、好きな本数のキューを作成
- **プレイリスト URL 生成**: `youtube.com/watch_videos?video_ids=...` 形式で公式アプリにバトンを渡す
- **キュー操作**: 前 / 次 / 任意動画タップ / 再シャッフル
- **API キー保存**: `localStorage` にブラウザ内のみ保持

## 使い方

1. [Google Cloud Console](https://console.cloud.google.com/) で YouTube Data API v3 を有効化し API キーを取得
2. ツールを開いて API キーとチャンネル URL を入力
3. 「シャッフル開始」をタップしてキューを生成
4. 「YouTube で開く」をタップすると公式 YouTube が開き、生成されたプレイリストを順次再生
   - YouTube Premium 加入者ならバックグラウンド再生・スリープ中再生が自動で適用されます

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
- API キーは `localStorage` の `yt_api_key` に保存
- ダーク UI（`#0a0a0a` ベース、アクセント `#ff3d3d` → `#ff8c42`）
- レスポンシブ（モバイル最適化、最小タップ領域 44px 以上）

## 制限事項

- API キーが必須。クライアントサイドで利用するため、HTTP リファラ制限の付与を強く推奨
- `watch_videos` URL は YouTube 側の仕様で、長すぎる ID 列は途中で切られる可能性あり
- メンバーシップ限定動画やプレミアの予定動画は取得元の `uploads` プレイリストに含まれない場合あり
- API クォータ（既定で 10,000 ユニット/日）の制約を受ける
