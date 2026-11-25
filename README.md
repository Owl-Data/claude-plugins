# Owl Data の Claude Code プラグイン

株式会社Owl Data が配っている、Claude Code 向けのプラグインです。

## Owl Suite

Owl Suite（Owl DB・Owl CRM・Owl Deal など）を、Claude Code から使うための接続（MCP）です。
ログインして許可すると、あなたの権限で、会社・コンタクト・案件・活動などを読み書きできます。

### 入れ方

Claude Code で、次の 2 つを順に実行します。

```
/plugin marketplace add Owl-Data/claude-plugins
/plugin install owl-suite@owl-data
```

そのあと Claude Code を起動し直し、`/mcp` で `owl-suite` を選んで「Authenticate」を押します。ブラウザに Owl Suite の許可の画面が出るので、連携先の組織とアカウントを確かめて「許可」を押してください。

### 接続用のURLを変える（組織ごとのURLを使うとき）

何も設定しなければ `https://suite.owl-data.jp/mcp` に接続します。Owl Suite の 設定 ＞ APIトークン ＞ 接続方法 に別のURL（`https://suite.owl-data.jp/o/<組織の短い名前>/mcp`）が表示されている場合は、次を実行してそのURLを入れ、Claude Code を起動し直してください。

```
/plugin configure owl-suite@owl-data
```

### 知っておくこと

- 使えるのは、Owl Suite のアカウントを持っている人だけです。
- 1 つの接続でつながるのは、1 つの組織です。
- 操作できる範囲は、あなたの権限と同じです。書き込みは、操作履歴に「Claude から」と記録されます。
- 削除・統合・メールの送信は、ここからはできません（Owl Suite の画面で行います）。
- 連携は、Owl Suite の 設定 ＞ APIトークン の「連携アプリ」でいつでも解除できます。
- 同じURLを、Claude のコネクタや `claude mcp add` でもう接続している場合、このプラグインの接続は重複として表示されません（先に接続したほうが使われます）。
- claude.ai・Claude Desktop でも使うときは、プラグインではなく、Claude の「設定」→「コネクタ」→「カスタムコネクタを追加」から同じURLで接続してください。

### Privacy

[プライバシーポリシー](https://owl-data.jp/privacy/)
