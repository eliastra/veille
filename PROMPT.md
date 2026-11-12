Lis source.yaml. Récupère les articles des 14 derniers jours de chaque source.
Exclus tout article dont le sujet principal est une CVE/faille (voir `exclude`).
Lis les 30 derniers messages de mon DM Slack et ignore les liens déjà envoyés.
Choisis 5 articles les plus utiles pour inspirer des propositions à des clients cloud
(postmortems, architectures de référence, solutions populaires). Varie les sources et les types.
Public : les SRE du Run Theodo, qui opèrent l'infra cloud de clients (Kubernetes, Terraform, CI/CD, monitoring, incidents, coûts, sécurité, montées de version).
Garde uniquement les articles actionnables pour ce travail : ce qu'on peut appliquer, proposer ou vérifier chez un client.
Exclus ce qui concerne le métier du fournisseur plutôt que celui de l'opérateur : consommation énergétique ou refroidissement de datacenters, annonces de résultats ou de levées de fonds, partenariats, nouveaux datacenters ou régions sans impact pratique, produits sans lien avec l'infra, IA ou ML sans angle infra/ops.
Envoie-moi un seul DM Slack en français. Pour chaque article, ce format exact :

# <emoji> Titre informatif
1-2 phrases : ce qui s'est passé / la solution, et pourquoi c'est utile pour un client.
_<lien|Source>_

Règles du titre :
- Un emoji en tout début de titre, qui reflète le sujet (🔥 incident, 🏗️ architecture, 💸 coûts, 🔐 sécurité, 📈 scalabilité, 🛠️ outil, 🇫🇷 cloud français, autre).
- Titre en heading H1 Markdown (ligne commençant par `# `), ni en gras ni en italique, compréhensible par quelqu'un qui n'a pas lu l'article.
- Dis ce que l'article apporte au lecteur (le bénéfice, le problème résolu), pas le jargon technique interne.
- Pas de nom de protocole ou d'algo non expliqué. Pas de clickbait creux.

Exemples de bons titres :
- # 🏗️ Comment Azure anticipe les pannes matérielles, et comment en profiter
- # 🔥 Pourquoi une simple mise à jour de config a coupé Cloudflare pendant 30 minutes
- # 💸 Comment Spotify a réduit de 40 % sa facture Kubernetes sans toucher aux applications
- # 📈 Comment tenir 10 fois plus de trafic sans tout réécrire : le cas Doctolib
- # 🇫🇷 Comment Scaleway a simplifié la gestion de ses clusters Kubernetes managés

Exemples de mauvais titres (à éviter) :
- Cloudflare abandonne Raft/Paxos pour un consensus qui ne cale jamais (jargon, incompréhensible hors spécialistes)
- Retour d'expérience sur notre migration (vague, ne dit rien)
- Vous ne croirez jamais ce qui a cassé notre prod (clickbait)

Exemple complet :
# 🔥 Pourquoi une simple mise à jour de config a coupé Cloudflare pendant 30 minutes
Une règle WAF mal testée a saturé le CPU de tous les serveurs en quelques secondes. Utile pour proposer à un client un déploiement progressif des changements de config, avec rollback automatique.
_<https://blog.cloudflare.com/exemple|Cloudflare>_

Pas d'intro, pas de conclusion. Pas d'autre emoji que celui du titre. Ne mets que des liens que tu as réellement ouverts.
