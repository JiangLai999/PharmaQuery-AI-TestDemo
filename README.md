# PharmaQuery-AI-TestDemo

**10-minute verifiable AI pipeline for drug search / 10 分钟可验证的 AI 药品搜索流程 — BERT embeddings + Collaborative Filtering.**

> No MySQL, no Java, no WeChat. Just Python + 3 commands.
> 无需 MySQL / Java / 微信小程序。仅需 Python + 3 条命令。

## Quick Start / 快速启动

```bash
git clone https://github.com/JiangLai999/PharmaQuery-AI-TestDemo.git
cd PharmaQuery-AI-TestDemo
pip install -r requirements.txt
python run_demo.py
```

> First run downloads ~118 MB model. Subsequent runs are instant.
> 首次运行下载约 118 MB 模型，后续运行立即执行。

## What This Demo Proves / 本 Demo 验证内容

| Workflow / 工作流 | Engine / 引擎 | Real AI / 真实 AI? |
|---|---|---|
| 1. Semantic Drug NER / 语义药品匹配 | BERT embeddings (384-dim) → cosine matching / BERT 嵌入 → 余弦匹配 | ✅ |
| 2. Drug Similarity / 药品相似度 | BERT embedding cosine distance / BERT 嵌入余弦距离 | ✅ |
| 3. Personalized Recommendation / 个性化推荐 | User-Based Collaborative Filtering / 基于用户的协同过滤 | ✅ |

### Key Result / 关键结果："抗生素" vs "头孢类药物"

- Jaccard（character overlap / 字符重叠）：**0.00** — zero shared characters，keyword match fails / 零共同字符，关键词匹配失败
- BERT（semantic embedding / 语义嵌入）：**0.73** — model learned cephalosporins are antibiotics from training data / 模型从训练数据中学到了头孢类药物是抗生素的子类

## Screenshots / 运行截图

### Workflow 1 / 工作流 1：Real AI Semantic NER / 真实 AI 语义药品匹配

![NER Demo](images/testdemo1.png)

### Workflow 2 / 工作流 2：Real AI Semantic Similarity / 真实 AI 语义相似度

![Similarity Demo](images/testdemo2.png)

### Workflow 3 / 工作流 3：Collaborative Filtering Recommendation / 协同过滤推荐

![CF Part 1](images/testdemo3.png)

![CF Part 2](images/testdemo4.png)

### Test Results / 测试结果（11/11 Passing / 全部通过）

![Test Results](images/testdemo5.png)

## Run Tests / 运行测试

```bash
python -m unittest test_demo.py -v
```

## Files / 文件说明

| File / 文件 | Purpose / 用途 |
|---|---|
| `ai_engine.py` | BERT model loader + inference / BERT 模型加载与推理 |
| `run_demo.py` | 3 AI workflow demo / 3 个 AI 工作流演示 |
| `test_demo.py` | 11 automated tests / 11 个自动化测试 |
| `results.json` | Sample output / 示例输出 |
| `DEBUG_LOG.md` | Real debugging log / 真实排错记录 |
| `AI_COLLABORATION.md` | AI agent collaboration record / AI 智能体协作记录 |

## Model / 模型

`paraphrase-multilingual-MiniLM-L12-v2` — 118M parameters / 1.18 亿参数，384-dim embeddings / 384 维向量，50+ languages including Chinese / 支持包括中文在内的 50+ 语言。
