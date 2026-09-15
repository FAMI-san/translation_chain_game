# 翻訳繋ぎゲーム

英単語を起点に英和辞書と和英辞書を交互に引き、日本語と英語をつないだネットワーク（翻訳地図）を作る授業活動のウェブアプリ。

## 現状

作業空間の実装は Claude Design 上で進行中。このリポジトリはコードそのものではなく、
仕様と将来の移行を受け止める箱として先に用意している。

## 構成

```
docs/                      仕様・原稿。実装より前にこちらが正
  workspace-requirements.md  作業空間の要件定義
  teacher-page-copy.md       先生向けページの原稿
app/                        Claude Design からエクスポートしたコードの置き場（現時点では空）
```

## 今後の流れ

1. Claude Design の `Export` からコードを取り出し、`app/` に置く
2. `docs/workspace-requirements.md` の「14. 将来の移行に備えて」に沿って、
   保存処理（`loadMap` / `saveMap` / `createMap`）とグラフの純粋処理を分離しているか確認する
3. 独立ウェブアプリへ移行する段になったら、`app/` の中身をバックエンド込みで置き換える。
   `docs/` の `Session` 形式（`v: 1`）は変えずに引き継ぐ

## 未解決の設計メモ

- 編集リンクの `k=<編集キー>` はURL上に露出する暫定の権限方式。
  本移行では扱いを見直す（`docs/workspace-requirements.md` 14.4 参照）
