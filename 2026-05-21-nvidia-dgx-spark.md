# NVIDIA DGX Spark 詳細ガイド（2026年）

Grace Blackwell スーパーチップ（GB10）を搭載した個人向けAIスーパーコンピューター。
150mm角・1.2kgのコンパクト筐体に、データセンター品質のAI性能を凝縮。
家庭用コンセント（240W）で動作する。

---

## スペック

| 項目 | 内容 |
|------|------|
| チップ | **GB10 Grace Blackwell Superchip** |
| CPU | 20コア Arm（Cortex-X925 × 10 + A725 × 10） |
| GPU | Blackwell（FP4：**1 PFLOPS**） |
| メモリ | **128GB LPDDR5x 統合メモリ**（CPU・GPU共有） |
| 内部帯域 | NVLink-C2C 900 GB/s（PCIe 5の5倍） |
| ストレージ | 4TB SSD |
| NIC | ConnectX-7（200 Gbps） |
| 消費電力 | 240W（家庭用コンセント対応） |
| サイズ | 150mm角・重量1.2kg |
| 価格 | **$4,699**（2026年2月に$3,999から値上げ） |

---

## LLM性能ベンチマーク

| モデル | 速度 | 備考 |
|--------|------|------|
| Llama 3.2 90B | 4.6 tok/s | 初回トークンまで133秒 |
| DeepSeek R1 70B | 4.6 tok/s | 初回トークンまで180秒 |
| Gemma 1B（Q4） | 204 tok/s | RTX 5090（160 tok/s）を上回る |

**弱点**：LPDDR5xのためTime to First Token（最初の文字が出るまでの時間）が長い。
大規模モデルでは数分待つケースがある。

---

## RTX 5090との比較

| 項目 | DGX Spark | RTX 5090 |
|------|-----------|---------|
| VRAM / メモリ | **128GB**（統合） | 32GB（GDDR7） |
| 対応モデル上限 | **〜200Bパラメータ** | 〜70B（量子化前提） |
| 推論速度（大規模） | 遅め（4〜5 tok/s） | 速め |
| 価格 | $4,699 | 〜$2,000 |
| NVLink拡張 | **2台接続で256GB** | 非対応 |

---

## 2台接続で405Bモデルも動く

DGX Sparkは2台をConnectX-7（200Gbps）で直結すると**256GBの統合メモリプール**を形成し、
**405Bパラメータ**のモデルまで推論可能になる。

---

## ローカルLLM構築の選択肢まとめ

| 予算 | 目的 | おすすめ |
|------|------|---------|
| 〜30万円 | 7B〜13B推論 | RTX 5090 × 1 |
| 〜80万円 | 70B〜200B推論 | DGX Spark × 1 |
| 〜160万円 | 200B〜405B推論 | DGX Spark × 2（直結） |
| 〜100万円 | 70B推論（Mac環境） | Mac Studio M4 Ultra |
| 〜300万円〜 | 本格的な学習・大規模推論 | 中古H100 × 複数枚 |

---

## 購入できる場所

- NVIDIA公式マーケットプレイス
- Micro Center
- Newegg
- Best Buy

---

## こんな人に向いている

- 70B〜200Bの大規模モデルをローカルで動かしたい開発者・研究者
- CUDAエコシステムをそのまま使いたい
- RTX 5090ではVRAMが足りないが、データセンター契約は予算オーバー

---

## ソース

- [NVIDIA DGX Spark 公式](https://www.nvidia.com/en-us/products/workstations/dgx-spark/)
- [DGX Spark Complete Guide 2026 — ToolHalla](https://toolhalla.ai/blog/nvidia-dgx-spark-complete-guide-2026/)
- [DGX Spark Review — IntuitionLabs](https://intuitionlabs.ai/articles/nvidia-dgx-spark-review)
- [DGX Spark GB10 vs RTX 5090 ベンチマーク — ProxPC](https://www.proxpc.com/blogs/nvidia-dgx-spark-gb10-performance-test-vs-5090-llm-image-and-video-generation)
- [Micro Center 購入ページ](https://www.microcenter.com/product/699008/nvidia-dgx-spark)

## 購入計画の策定


