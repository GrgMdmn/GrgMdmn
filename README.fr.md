# Grégoire Mureau

📘 This profile is also available in [English 🇬🇧](https://github.com/GrgMdmn/GrgMdmn/blob/main/README.md)

**Ingénieur ML / data — RAG · serving LLM · homelab Kubernetes**

Diplômé **AI Engineer (Data Science Expert)**. 18 mois d’ingénierie de données en production à l’[Ifremer](https://www.ifremer.fr/) (Copernicus Marine, millions d’observations in situ / jour ; [3 publications scientifiques](https://www.researchgate.net/profile/Gregoire_Mureau)).

J’administre aussi mon infra : deux machines **Ubuntu Server**, deux clusters **k3s indépendants** — l’une **calcule**, l’autre **expose**. Ce compte GitHub est le miroir public. Source de vérité au quotidien : [git.gregoiremureau.com](https://git.gregoiremureau.com/grgmro).

## Homelab — une machine calcule, l’autre expose

Les clusters **ne sont pas** fédérés : si l’une des machines tombe, l’autre continue de servir. Liaison Tailscale.

| | **Mini PC** (calcul) | **NAS** (mise à disposition) |
|---|---|---|
| Matériel | AMD Ryzen 7 8745HS · iGPU Radeon 780M · 48 Go RAM unifiée | Intel N100 · 31 Go · MergerFS + SnapRAID |
| Rôle | Inférence GPU, runners CI, observabilité | Bordure publique : Traefik, git, cloud, démos ML |
| Orchestration | k3s (single-node) | k3s (single-node) |

La 780M est une iGPU modeste, **sans VRAM dédiée**. Une dGPU dans le même format (mini PC / laptop) plafonne en général à 8–16 Go de VRAM ; ici les poids tiennent dans la **RAM unifiée** (GTT, plusieurs dizaines de Gio). C’est ce qui permet d’héberger et de servir un MoE comme Qwen3-30B-A3B, trop volumineux pour la VRAM d’une carte discrète équivalente.

**Démo LLM** (chat temporaire, rien n’est conservé) : [Qwen3-30B MoE via Open WebUI](https://llm.gregoiremureau.com/auto-login.html?temporary-chat=true&model=qwen3:30b-a3b-q6k)

Aussi servis par le NAS : [APIs ML](https://api.gregoiremureau.com/ml/) · Forgejo : [git.gregoiremureau.com](https://git.gregoiremureau.com).

## Étude de cas — communauté migrée vers une plateforme souveraine

Communauté ouverte en 2007 (19 ans, bientôt 20), d’abord sur une plateforme propriétaire, puis une deuxième, migrée vers **Discourse** (open source) sur un **VPS dédié** que j’administre — pas sur le NAS : **[depiedencap.org](https://depiedencap.org/)**.

- 22 230 sujets · 424 835 messages · 7 102 comptes mappés · 93 884 images (8,8 Go)
- Plugins Discourse custom (onboarding, locale FR/PWA, citations RAG)
- Mail & RGPD : campagnes de réactivation, droit à l’effacement avec dossiers de preuve
- RAG sur le corpus des **fils** (embeddings **bge-m3** → pgvector → Qwen3-30B sur le mini PC) — l’assistant n’indexe pas les profils

Le code de scraping et les données membres restent privés. Ici : l’architecture et les résultats.

## Master AI Engineer — OpenClassrooms

Un dépôt par projet (issu de l’ancien monorepo). Mêmes noms sur l’organisation Forgejo [`openclassroom-ai`](https://git.gregoiremureau.com/openclassroom-ai).

| # | Projet | GitHub | Live |
|---|---|---|---|
| 2 | Paris trees (Pandas, Folium) | [oc-p02-paris-trees](https://github.com/GrgMdmn/oc-p02-paris-trees) | — |
| 3 | OpenFoodFacts | [oc-p03-openfoodfacts](https://github.com/GrgMdmn/oc-p03-openfoodfacts) | — |
| 4 | Scoring crédit (LightGBM, SHAP, LIME) | [oc-p04-credit-scoring](https://github.com/GrgMdmn/oc-p04-credit-scoring) | — |
| 5 | Segmentation client Olist | [oc-p05-customer-segmentation](https://github.com/GrgMdmn/oc-p05-customer-segmentation) | — |
| 6 | Classification produits (NLP + CV) | [oc-p06-product-classification](https://github.com/GrgMdmn/oc-p06-product-classification) | — |
| 7 | Analyse de sentiment (LSTM, DistilBERT) | [oc-p07-sentiment-api](https://github.com/GrgMdmn/oc-p07-sentiment-api) | [démo](https://api.gregoiremureau.com/ml/sentiment/) |
| 8 | Street vision (U-Net, FPN) | [oc-p08-street-vision](https://github.com/GrgMdmn/oc-p08-street-vision) | [démo](https://api.gregoiremureau.com/ml/street-vision/) |
| 9 | Street vision PoC (SegFormer vs FPN) | [oc-p09-street-vision-poc](https://github.com/GrgMdmn/oc-p09-street-vision-poc) | [démo](https://api.gregoiremureau.com/ml/street-vision-poc/) |
| 10 | Recommandation de contenu | [oc-p10-content-recommendation](https://github.com/GrgMdmn/oc-p10-content-recommendation) | — |
| 11 | Big data fruits (PySpark) | [oc-p11-bigdata-fruits](https://github.com/GrgMdmn/oc-p11-bigdata-fruits) | — |
| 12 | Cadrage Fashion-Insta | [oc-p12-fashion-insta](https://github.com/GrgMdmn/oc-p12-fashion-insta) | — |

Landing ML : [api.gregoiremureau.com/ml/](https://api.gregoiremureau.com/ml/) · l’ancien monorepo est une archive (privé).

## Liens

- Site : [gregoiremureau.com](https://www.gregoiremureau.com)
- Forgejo : [git.gregoiremureau.com/grgmro](https://git.gregoiremureau.com/grgmro)
- LinkedIn : [gregoire-mureau](https://www.linkedin.com/in/gregoire-mureau-a7455a19b/)
- Publications : [ResearchGate](https://www.researchgate.net/profile/Gregoire_Mureau)
- Produce Estimates (PWA React, démo anonymisée) : [demo.gregoiremureau.com/estimaciones_demo/](https://demo.gregoiremureau.com/estimaciones_demo/)
