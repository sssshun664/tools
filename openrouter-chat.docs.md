# OpenRouter Chat

OpenRouter APIを使用したシンプルなチャットアプリケーション。スマートフォンからのアクセスに最適化されています。

## 機能

- **OpenRouter API統合**: 様々なLLMモデルとチャット可能
- **ストリーミングレスポンス**: リアルタイムで応答を表示
- **トークン使用情報**: 各応答のトークン数を表示（推論トークンを含む）
- **システムプロンプト設定**: AIの振る舞いや役割をカスタマイズ可能
- **設定の永続化**: APIキー、モデル名、システムプロンプト、チャット履歴をLocalStorageに保存
- **モバイルフレンドリー**: スマートフォンでの使用に最適化されたUI
- **キーボードショートカット**: Enter で送信、Shift+Enter で改行

## 使い方

### 初期設定

1. ブラウザで `openrouter-chat.html` を開く
2. 「⚙️ 設定」ボタンをクリック
3. OpenRouter API Keyを入力
   - APIキーは [OpenRouter](https://openrouter.ai/keys) で取得できます
4. 使用したいモデル名を入力（任意）
   - デフォルト: `google/gemini-3-flash-preview`
5. システムプロンプトを設定（任意）
   - デフォルト: 「あなたは親切で知識豊富なAIアシスタントです。ユーザーの質問に丁寧に答えてください。」
   - AIの振る舞いや役割をカスタマイズできます

### チャット

1. 下部のテキストエリアにメッセージを入力
2. 「送信」ボタンをクリック、または Enter キーを押す
3. AIの応答がリアルタイムでストリーミング表示されます
4. 応答の下部にトークン使用情報が表示されます

### その他の機能

- **チャット履歴のクリア**: 設定画面から「チャット履歴をクリア」ボタンをクリック
- **改行の挿入**: メッセージ入力時に Shift+Enter で改行

## 技術仕様

- **API**: OpenRouter REST API v1
- **ストリーミング**: Server-Sent Events (SSE)
- **ストレージ**: LocalStorage（APIキー、モデル名、チャット履歴）
- **依存関係**: なし（純粋なHTML/CSS/JavaScript）

## 利用可能なモデル例

- `google/gemini-3-flash-preview` - Gemini 3 Flash Preview
- `anthropic/claude-3.5-sonnet` - Claude 3.5 Sonnet
- `openai/gpt-4-turbo` - GPT-4 Turbo
- その他のモデルは [OpenRouter Models](https://openrouter.ai/models) を参照

## プライバシーとセキュリティ

- APIキーとチャット履歴はブラウザのLocalStorageに保存されます
- データは外部サーバーには送信されません（OpenRouter API以外）
- APIキーは必ず自分で管理し、他人と共有しないでください

## トラブルシューティング

### APIエラーが発生する

- APIキーが正しいか確認してください
- モデル名が正しいか確認してください
- OpenRouterのクレジットが十分か確認してください

### チャット履歴が消えた

- LocalStorageがクリアされた可能性があります
- ブラウザのプライベートモードでは履歴は保存されません

### モバイルでキーボードが表示されない

- テキストエリアをタップしてください
- ブラウザを再読み込みしてみてください
