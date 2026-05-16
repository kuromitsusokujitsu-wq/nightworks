# Layer 3 — チーム編成

## 組織図

```
CEO（ユーザー / 株式会社X-Style 代表）
 └─ 7 機能エージェント（.claude/agents/）
     ├─ sales-automator      営業オートメーター
     ├─ customer-success     伴走者（オンボーディング/解約防止）
     ├─ researcher           公募要領アナリスト
     ├─ drafter              申請書ドラフター
     ├─ reviewer             辛口審査員
     ├─ kpi-analyst          数字の番人
     └─ compliance-guardian  法務番人（最上位の拒否権）
```

CEO は最終意思決定者。撤退/ピボット・価格・新規公募対応・予算>¥1万・法務グレーは CEO 決裁。

## 権限と上申ルール

| エージェント | 通常権限 | 上申条件 |
|---|---|---|
| sales-automator | 公開名簿からのリスト生成・文面生成・送信レート制御 | 送信ドメイン評判低下、特商法判断の迷い |
| customer-success | オンボーディング定型実施・FAQ回答・解約予兆検知 | 解約申し出、契約条件の例外要望 |
| researcher | 公募要領の構造化・要件チェックリスト化 | 公募要領の解釈が割れる/新規公募 |
| drafter | 構造化要件に基づく下書き生成 | ヒアリング情報の重大な不足 |
| reviewer | 加点基準採点・差し戻し | 2周しても合格点未達 |
| kpi-analyst | 週次KPI更新・ライン監視 | 撤退/ピボットライン抵触（即CEO） |
| compliance-guardian | 全納品前ゲート・停止権 | 第一原則抵触（即時・最優先でCEO） |

## ワークフロー連携図

```
[新規開拓]
 sales-automator ──(返信を 興味/質問/拒否/不在 に分類)──┐
                                                        ▼
[受注・着手]                                  customer-success(オンボーディング)
                                                        │
[案件処理ループ]                                         ▼
 researcher(公募要領→構造化要件)
     │
     ▼
 drafter(要件＋ヒアリング→下書き)
     │
     ▼
 reviewer(加点基準で添削) ──不合格──▶ drafter へ差し戻し(既定2周)
     │ 合格
     ▼
 compliance-guardian(行政書士法/特商法/個人情報 3点ゲート) ──抵触──▶ 停止＋CEO上申
     │ 通過
     ▼
 行政書士へ納品
     │
     ▼
[継続]
 customer-success(継続支援/解約防止)   kpi-analyst(週次でMRR・ファネル・撤退ライン監視)
```
