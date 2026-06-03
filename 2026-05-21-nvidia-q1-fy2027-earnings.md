# Nvidia Q1 FY2027 決算まとめ（2026年5月20日発表）

## 実績（vs 市場予想）

| 指標 | 実績 | 市場予想 | 差 |
|------|------|----------|----|
| 売上高 | **$81.6B** | $79.2B | +3.9% |
| EPS（非GAAP） | **$1.87** | $1.77 | +6.6% |
| 前年同期比売上成長 | **+85%** | — | — |

---

## Q2 FY2027 ガイダンス

| 指標 | ガイダンス |
|------|-----------|
| 売上高 | **$91.0B**（±2%） |
| 粗利率（GAAP） | 74.9%（±0.5pp） |
| 粗利率（非GAAP） | 75.0%（±0.5pp） |

市場コンセンサスは $86〜87B だったため、**$91B は大幅上振れ**。

---

## セグメント別売上

今回より報告区分を以下の2セグメントに再編：

| セグメント | 売上 | 前四半期比 |
|-----------|------|-----------|
| **Hyperscale**（大手クラウド向け） | $38B | +12% |
| **ACIE**（AIクラウド・産業・エンタープライズ） | $37B | +31% |
| データセンター合計 | **$75B** | +21% |
| フリーキャッシュフロー | **$49B** | 過去最高 |

---

## 決算説明会（Earnings Call）主要内容

### Jensen Huang 冒頭発言

- 「AIは今や生産的・経済的価値を生む仕事ができる。**トークンが収益を生む時代になった**」
- 「**アジェンティックAIが到来した**。AIエージェントが自律的にタスクを実行する時代」
- Blackwellは「自社史上最速の製品立ち上げ」と表現。GB300・GH200が超大手クラウドとモデル開発会社に急速採用

### 新製品・プラットフォーム

**Vera CPU（新発表）**
- アジェンティックAI向けに設計した自社初のCPU
- 「Nvidiaがこれまで参入したことのない **$200B（約30兆円）の新市場**を開拓」
- 2026年内に単体で約 **$20B** の売上を見込む
- CPUはエージェントのオーケストレーション、GPUは推論思考処理を担当——競合ではなく**相補関係**

**Vera Rubin プラットフォーム**
- 2026年Q3より量産出荷開始、以降順次拡大
- Huang：「Grace Blackwellを超える成功になるのは確実」

### 株主還元

- 配当：1株 $0.01 → **$0.25** に大幅引き上げ
- 自社株買い：**$80B**（約12兆円）の新枠承認

### 中国ビジネス

- H200の対中輸出ライセンスは米政府から承認済み
- ただし「**現時点で中国向けデータセンター収益はゼロ**」とHuangが明言
- Q2ガイダンスにも中国向け収益は含まれていない

### アナリストQ&A ポイント

- **セグメント再編の理由**：「AIビジネスは多様化しており、自社の事業をより深く理解するため」
- **CPU vs GPU 競合懸念**：「CPUとGPUは役割が異なり食い合いはない」と否定
- **推論市場のシェア**：「フロンティアモデルの推論はすべてNvidiaで動いている」

---

## 総評

売上・EPSともにビート、ガイダンスも大幅上振れという「完璧な決算」。Vera CPUによる新市場開拓と$80Bの自社株買いが新たなサプライズ要素。ただし株価の時間外反応は+1.57%にとどまり、高い期待値がすでに株価に織り込まれていた状況を示している。次の焦点はVera Rubinの量産スケジュールと中国向け収益の解禁タイミング。

---

## Vera Rubin 量産スケジュール詳細

### タイムライン

| 時期 | マイルストーン |
|------|--------------|
| 2026年Q1（既報） | フル生産入り（予定より前倒し） |
| **2026年Q3〜** | 量産出荷開始（NVL72 / NVL144） |
| 2026年末 | **Rubin CPX**（8 exaflops構成）投入 |
| 2027年後半 | **Rubin Ultra**（15 exaflops FP4）投入 |

Jensen Huangは「**予定より大幅に前倒しで量産に入った**」と強調。Blackwellの立ち上げ遅延を教訓に、TSMC・SK Hynix・Micronとの連携でHBM4の歩留まりを先に解決済み。

### 主要構成（NVL144）

| 仕様 | 内容 |
|------|------|
| GPU数 | 144ダイ（72パッケージ） |
| CPU | Vera CPU × 36（88コア・Arm独自設計） |
| 推論性能 | **3.6 exaFLOPS**（FP4） |
| メモリ | HBM4 288GB |
| スケールアップ帯域 | 260 TB/s（NVLink） |
| 消費電力 | 約120〜130kW/ラック |

NVL72（半構成）もラインナップ。

### 初期展開パートナー（H2 2026）

**ハイパースケーラー**: AWS・Google Cloud・Microsoft Azure・Oracle Cloud  
**クラウドパートナー**: CoreWeave・Lambda・Nebius・Nscale

### ロードマップ全体像

```
Blackwell (B300/GB300) → Vera Rubin NVL72/144 → Rubin CPX  → Rubin Ultra
  今（量産中）               2026年H2（出荷）    2026年末     2027年H2
  B300=GPU単体                 5 exaFLOPS         8 exaFLOPS  15 exaFLOPS
  GB300=Grace CPU+GPU込み
```

### 注目点

- Blackwellから**約5倍の性能向上**をHuangが強調
- Rubin Ultraは600kWラック構成が控えており、電力インフラ側の対応が次の課題
- 中国向け出荷はライセンス次第で未確定のため、量産規模はすべて西側向けが前提

---

## ソース

- [Nvidia NVDA Q1 FY2027 Earnings — CNBC Live Updates](https://www.cnbc.com/2026/05/20/nvidia-nvda-earnings-report-q1-2027.html)
- [Earnings Call Transcript — The Motley Fool](https://www.fool.com/earnings/call-transcripts/2026/05/20/nvidia-nvda-q1-2027-earnings-transcript/)
- [Earnings Call Transcript — Benzinga](https://www.benzinga.com/insights/news/26/05/52707551/transcript-nvidia-q1-2027-earnings-conference-call)
- [NVIDIA Q1 Revenue hits $81.6B — StockTitan](https://www.stocktitan.net/news/NVDA/nvidia-announces-financial-results-for-first-quarter-fiscal-fq78amc9h84m.html)
- [Nvidia Q2 Guidance Analysis — TechTimes](https://www.techtimes.com/articles/316918/20260520/nvidia-q1-fy2027-earnings-q2-guidance-above-87-billion-only-move-markets-will-reward.htm)
- [エヌビディア決算速報 — Investing.com Japan](https://jp.investing.com/news/earnings/article-1544287)
- [Nvidia Rubin full production ahead of schedule — WCCFTech](https://wccftech.com/nvidia-rubin-ai-chips-enter-full-production-well-ahead-of-schedule/)
- [Vera Rubin NVL72 詳細スペック — VideoCardz](https://videocardz.com/newz/nvidia-vera-rubin-nvl72-detailed-72-gpus-36-cpus-260-tb-s-scale-up-bandwidth)
- [Vera Rubin NVL144 — Awesome Agents](https://awesomeagents.ai/hardware/nvidia-vera-rubin-nvl144/)
- [Vera Rubin 600kW racks 2027 — Introl Blog](https://introl.com/blog/nvidia-vera-rubin-gpu-600kw-racks-2027)
