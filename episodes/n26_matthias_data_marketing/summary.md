# N26 — Matthias : Data for Marketing

> **Podcast** : Data & IA  
> **Invité** : Matthias, Head of Data for Marketing @ N26  
> **Contexte** : N26 — néobanque berlinoise, 5M+ clients, ~1 500 employés, valorisée à +9 milliards $

---

## 🏢 L'organisation data chez N26

- Pas de VP Data central : des équipes data **décentralisées par département**
- La team marketing est la seule équipe **full-stack** (analytics engineers + data analysts + data scientists)
- **12 personnes** au total, réunies sous Matthias après une consolidation progressive 2020–2024
- Les autres fonctions data centrales : data platform (~20), central analytics (~25), analytics engineering (~12), data science & products (~20)

---

## 🔬 Les deux projets phares

### 1. Marketing Mix Modeling (MMM)

**Problème** : les canaux offline (TV, affichage) ne sont pas trackables via le web. Les ad blockers et les contraintes privacy dégradent aussi le tracking classique.

**Solution** : modèle [Google Meridian](https://github.com/google/meridian) (Python), calibré en interne.

**Inputs** :
- Dépenses marketing par canal
- Événements internes (incidents, downtime) → *growth event logger* maison
- Données concurrents : Sensor Tower, SimilarWeb
- Facteurs macro : taux BCE, saisonnalité

**Output** :
- Signups attribués par canal et par jour
- Décomposition : baseline organique / media / saisonnalité / événements
- **Optimisation budgétaire** : quel channel mix pour un budget donné ?

**Autres frameworks MMM connus** : Robin (Meta), Orbit (Uber), PyMC3

---

### 2. User Value (proxy LTV)

**Pourquoi "User Value" et pas "Lifetime Value"** : N26 n'a pas encore 15 ans d'historique. La prédiction porte donc sur **2 ans** après la conversion.

**Objectif** : prédire les profits générés par un utilisateur sur 2 ans → optimiser pour un payback period de 2 ans (LTV/CAC > 1).

**Brique de base** : un **user P&L** — table par user × mois avec :
- Revenus : frais de transaction, abonnement, produits d'investissement…
- Coûts : support client, infrastructure…

**Gouvernance** : steering committee (Finance BP + CMO + project lead) pour aligner les méthodologies (ex : faut-il front-loader les revenus d'abonnement ?).

---

## 🎯 Objectif Nord Star

Relier **MMM** et **User Value** pour optimiser non plus le volume d'acquisitions, mais la **rentabilité des clients acquis**.

> Aujourd'hui : deux modèles séparés reliés par des heuristiques simples.  
> Cible : bridge complet entre les deux.

---

## 🛠️ Stack technique

| Couche | Outil |
|--------|-------|
| Cloud | AWS |
| ML platform | SageMaker |
| Data lake | S3 |
| Data warehouse | Redshift |
| Tracking | Snowplow |
| Transformation | dbt |
| Catalogue | OpenMetadata |
| Viz | Metabase |
| ETL | Homemade → migration vers Airflow |

**Philosophie** : open-source / source-available imposée par les contraintes réglementaires bancaires (third-party risk assessment).

---

## 🚀 Prochaine étape

Passer de produits **"pour la consommation humaine"** à des produits **"pour la consommation machine"** :
- **Next Best Action** : alimenter les CRM avec des signaux ML (churn détecté, upsell potentiel…)
- **Acquisition** : remonter les métriques de user value vers les plateformes marketing pour automatiser l'optimisation (au lieu de le faire manuellement)

---

## ⚠️ Défis

**Professionnels** :
- Instabilité des priorités en scale-up (produits, équipes, leadership)
- Modèles à reconstruire constamment (nouveaux produits = zéro historique)
- Re-éduquer les stakeholders à chaque changement de personnes

**Personnels** :
- Syndrome de l'imposteur lors de la transition IC → manager
- Switch mental clé : *"mon rôle n'est plus d'être le plus tech, mais d'enabler mon équipe"*

---

## 📚 Ressources recommandées

- **The Phoenix Project** — Gene Kim *(naissance du DevOps, très applicable à la data)*
- The DevOps Handbook — Gene Kim
- Accelerate — Nicole Forsgren
- The Unicorn Project — Gene Kim
- Fundamentals of Data Engineering — Joe Reis
- Data Mesh — Zhamak Dehghani
