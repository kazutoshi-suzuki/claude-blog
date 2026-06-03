# NvidiaのBlackwellアーキテクチャ：RTX 50シリーズ vs データセンター向けの違い

同じ「Blackwellアーキテクチャ」を採用しながら、コンシューマー向けと
データセンター向けでは設計思想が根本的に異なる。

---

## 製品ラインナップの全体像

| カテゴリ | 製品名 | 用途 |
|---------|--------|------|
| コンシューマー | RTX 5090 / 5080 / 5070… | ゲーム・映像制作・ローカルAI |
| データセンター（GPU単体） | B300 / B200 | クラウド・エンタープライズAI |
| データセンター（CPU+GPU） | GB300 / GB200 | 大規模推論・学習（Grace CPU込み） |

> **命名規則**：頭の「G」= Grace CPU が含まれる意味。B300はGPU単体、GB300はGrace CPU + B300 GPUのスーパーチップ。

---

## スペック比較

| 項目 | RTX 5090（コンシューマー） | B300（データセンター） |
|------|--------------------------|----------------------|
| メモリ種類 | **GDDR7** 32GB | **HBM3e** 288GB |
| メモリ帯域 | 1,792 GB/s | 8,000 GB/s（約4.5倍） |
| FP4性能 | 対応（Tensor Core） | **15 PFLOPS** |
| 消費電力 | 575W | 1,200W超 |
| 価格 | 約$2,000〜 | DGX構成（8枚）で$300K〜$350K |
| 販売形態 | 量販店・一般購入可 | エンタープライズ専用 |

---

## 設計思想の違い

### RTX 50シリーズ（GeForce）

- **目的**：ゲーム・映像制作・ローカルAI推論
- **メモリ**：GDDR7は帯域あたりコストが安く、コンシューマー価格帯を実現
- **適したモデル**：Llama 8B・Mistral 7BなどVRAM 32GB以内で動くモデル
- **強み**：コストパフォーマンス、一般購入のしやすさ

### B200 / B300（データセンター）

- **目的**：大規模モデルの学習・推論専用
- **メモリ**：HBMは絶対帯域と容量が圧倒的（288GBで70B〜数百Bパラメータモデルを1枚で処理可能）
- **適したモデル**：Llama 70B以上、マルチモーダル大規模モデル
- **強み**：NVLinkで複数枚を密結合してスケールアウト可能

---

## 共通点（同じBlackwellである理由）

- FP4 / FP6 Tensor Core対応（推論の高速化）
- Transformer Engine（第2世代）
- 基本的なCUDAアーキテクチャ

コアの演算思想は同じだが、メモリ容量・帯域・スケール・耐久性・冗長性が
データセンター向けでは桁違いに強化されている。

---

## 用途別の選び方

| やりたいこと | 適した製品 |
|------------|-----------|
| ゲーム・映像制作 | RTX 5090 / 5080 |
| ローカルでLLM（〜7B） | RTX 5070以上 |
| ローカルでLLM（〜70B） | RTX 5090（量子化前提） |
| クラウドで70B以上を推論 | B300 / GB300 |
| 大規模モデルの学習 | GB300 NVL72 / NVL144 |

---

## ソース

- [B200 vs RTX 5090 比較 — RunPod](https://www.runpod.io/gpu-compare/b200-vs-rtx-5090)
- [RTX 5090 vs H100 vs B200 — Spheron Blog](https://www.spheron.network/blog/rtx-5090-vs-h100-vs-b200/)
- [Nvidia Blackwell Architecture Deep Dive — Tom's Hardware](https://www.tomshardware.com/pc-components/gpus/nvidia-blackwell-architecture-deep-dive-a-closer-look-at-the-upgrades-coming-with-rtx-50-series-gpus)
- [NVIDIA B300 Specs & Pricing — Spheron Blog](https://www.spheron.network/blog/nvidia-b300-blackwell-ultra-guide/)
- [Decoding Nvidia's Blackwell Products — Modal](https://modal.com/blog/nvidia-blackwell)
