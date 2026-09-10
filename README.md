# Grégoire Mureau

📘 Ce profil est également disponible en [français 🇫🇷](https://github.com/GrgMdmn/GrgMdmn/blob/main/README-fr.md)

**ML / data engineer — RAG · LLM serving · homelab Kubernetes**

Graduate **AI Engineer (Data Science Expert)**. Eighteen months in production data engineering at [Ifremer](https://www.ifremer.fr/) (Copernicus Marine, millions of in-situ observations per day; [3 scientific publications](https://www.researchgate.net/profile/Gregoire_Mureau)).

I also design and operate my own infrastructure: two **Ubuntu Server** machines, two independent **k3s** clusters — one that **computes**, one that **serves**. This GitHub account is the public mirror. Day-to-day source of truth: [git.gregoiremureau.com](https://git.gregoiremureau.com/grgmro).

## Homelab — compute vs serve

The clusters are **not** federated: if one machine is down, the other keeps serving. They talk over Tailscale.

| | **Mini PC** (compute) | **NAS** (serve) |
|---|---|---|
| Hardware | AMD Ryzen 7 8745HS · Radeon 780M iGPU · 48 GB unified RAM | Intel N100 · 31 GB · MergerFS + SnapRAID |
| Role | Inference, CI runners, observability | Public edge: Traefik, git, cloud, ML demos |
| Orchestration | k3s (single-node) | k3s (single-node) |

The 780M is a modest iGPU **with no dedicated VRAM**. A discrete GPU in the same form factor (mini PC / laptop) typically tops out at 8–16 GB of VRAM; here model weights sit in **unified memory** (GTT, tens of GiB). That is what makes it possible to host and serve an MoE such as Qwen3-30B-A3B, which would not fit in the VRAM of an equivalent dGPU.

**Try it** (temporary chat, nothing persisted): [Qwen3-30B MoE via Open WebUI](https://llm.gregoiremureau.com/auto-login.html?temporary-chat=true&model=qwen3:30b-a3b-q6k)

Also live from the NAS: [ML APIs](https://api.gregoiremureau.com/ml/) · Forgejo at [git.gregoiremureau.com](https://git.gregoiremureau.com).

## Case study — sovereign community platform

A community founded in 2007 (19 years, approaching 20), hosted first on one proprietary platform then a second, migrated to open-source **Discourse on a dedicated VPS I operate** (not on the NAS): **[depiedencap.org](https://depiedencap.org/)**.

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

ML demos: [api.gregoiremureau.com/ml/](https://api.gregoiremureau.com/ml/) · the former monorepo is an archive (private).

## Links

- Website: [gregoiremureau.com](https://www.gregoiremureau.com)
- Forgejo: [git.gregoiremureau.com/grgmro](https://git.gregoiremureau.com/grgmro)
- LinkedIn: [gregoire-mureau](https://www.linkedin.com/in/gregoire-mureau-a7455a19b/)
- Publications: [ResearchGate](https://www.researchgate.net/profile/Gregoire_Mureau)
- Produce Estimates (React PWA, anonymised demo): [demo.gregoiremureau.com/estimaciones_demo/](https://demo.gregoiremureau.com/estimaciones_demo/)
