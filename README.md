# Grégoire Mureau

**ML / data engineer — RAG · LLM serving · homelab Kubernetes**

Graduate **AI Engineer (Data Science Expert)**. Eighteen months in production data engineering at [Ifremer](https://www.ifremer.fr/) (Copernicus Marine, millions of in-situ observations per day; [3 scientific publications](https://www.researchgate.net/profile/Gregoire_Mureau)).

I also design and operate my own infrastructure: two **Ubuntu Server** machines, two independent **k3s** clusters — one that **computes**, one that **serves**. This GitHub account is the public mirror. Day-to-day source of truth: [git.gregoiremureau.com](https://git.gregoiremureau.com/grgmro).

## Homelab — compute vs serve

A rural internet outage must not take everything down, so the clusters are **not** federated. They talk over Tailscale.

| | **Mini PC** (compute) | **NAS** (serve) |
|---|---|---|
| Hardware | AMD Ryzen 7 8745HS · Radeon 780M iGPU · 48 GB unified RAM | Intel N100 · 31 GB · MergerFS + SnapRAID |
| Role | Inference, CI runners, observability | Public edge: Traefik, git, cloud, ML demos |
| Orchestration | k3s (single-node) | k3s (single-node) |

The 780M is a modest iGPU. I mainly run **MoE** models (Qwen3-30B-A3B) that stay snappy because they sit in **unified memory** (GTT), not dedicated VRAM — a deliberate architecture choice, not a discrete GPU workstation.

**Try it** (temporary chat, nothing persisted): [Qwen3-30B MoE via Open WebUI](https://llm.gregoiremureau.com/auto-login.html?temporary-chat=true&model=qwen3:30b-a3b-q6k)

Also live from the NAS: [ML APIs](https://api.gregoiremureau.com/ml/) · [MLflow](https://mlflow.gregoiremureau.com) · this Forgejo instance at [git.gregoiremureau.com](https://git.gregoiremureau.com).

## Case study — sovereign community platform

A community founded in 2007 (19 years, approaching 20), hosted first on one proprietary platform then a second, migrated to a fully self-hosted open-source Discourse: **[depiedencap.org](https://depiedencap.org/)**.

- 22,230 topics · 424,835 posts · 7,102 accounts mapped · 93,884 images (8.8 GB)
- Custom Discourse plugins (onboarding, French locale/PWA, RAG citations)
- Mail & GDPR ops: reactivation campaigns, erasure workflow with evidence files
- RAG on the thread corpus (embeddings **bge-m3** → pgvector → Qwen3-30B on the mini PC). Indexes **topics**, not user profiles.

Scraping pipelines and member data stay private — this page is architecture and outcomes, not a source dump.

## Master AI Engineer — OpenClassrooms

One repository per project (split from the old monorepo). Same names on Forgejo org [`openclassroom-ai`](https://git.gregoiremureau.com/openclassroom-ai).

| # | Project | GitHub | Live |
|---|---|---|---|
| 2 | Paris trees (Pandas, Folium) | [oc-p02-paris-trees](https://github.com/GrgMdmn/oc-p02-paris-trees) | — |
| 3 | OpenFoodFacts | [oc-p03-openfoodfacts](https://github.com/GrgMdmn/oc-p03-openfoodfacts) | — |
| 4 | Credit scoring (LightGBM, SHAP, LIME) | [oc-p04-credit-scoring](https://github.com/GrgMdmn/oc-p04-credit-scoring) | — |
| 5 | Olist customer segmentation | [oc-p05-customer-segmentation](https://github.com/GrgMdmn/oc-p05-customer-segmentation) | — |
| 6 | Product classification (NLP + CV) | [oc-p06-product-classification](https://github.com/GrgMdmn/oc-p06-product-classification) | — |
| 7 | Sentiment analysis (LSTM, DistilBERT) | [oc-p07-sentiment-api](https://github.com/GrgMdmn/oc-p07-sentiment-api) | [demo](https://api.gregoiremureau.com/ml/sentiment/) |
| 8 | Street vision (U-Net, FPN) | [oc-p08-street-vision](https://github.com/GrgMdmn/oc-p08-street-vision) | [demo](https://api.gregoiremureau.com/ml/street-vision/) |
| 9 | Street vision PoC (SegFormer vs FPN) | [oc-p09-street-vision-poc](https://github.com/GrgMdmn/oc-p09-street-vision-poc) | [demo](https://api.gregoiremureau.com/ml/street-vision-poc/) |
| 10 | Content recommendation | [oc-p10-content-recommendation](https://github.com/GrgMdmn/oc-p10-content-recommendation) | — |
| 11 | Big data fruits (PySpark) | [oc-p11-bigdata-fruits](https://github.com/GrgMdmn/oc-p11-bigdata-fruits) | — |
| 12 | Fashion-Insta project framing | [oc-p12-fashion-insta](https://github.com/GrgMdmn/oc-p12-fashion-insta) | — |

ML demos: [api.gregoiremureau.com/ml/](https://api.gregoiremureau.com/ml/) · former monorepo [`OpenClassrooms_AI_Projects`](https://github.com/GrgMdmn/OpenClassrooms_AI_Projects) is an archive.

## Links

- Website: [gregoiremureau.com](https://www.gregoiremureau.com)
- Forgejo: [git.gregoiremureau.com/grgmro](https://git.gregoiremureau.com/grgmro)
- LinkedIn: [gregoire-mureau](https://www.linkedin.com/in/gregoire-mureau-a7455a19b/)
- Publications: [ResearchGate](https://www.researchgate.net/profile/Gregoire_Mureau)
- Produce Estimates (React PWA, anonymised demo): [demo.gregoiremureau.com/estimaciones_demo/](https://demo.gregoiremureau.com/estimaciones_demo/)
