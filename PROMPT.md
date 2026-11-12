Lis source.yaml. Récupère les articles des 14 derniers jours de chaque source.
Exclus tout article dont le sujet principal est une CVE/faille (voir `exclude`).
Lis les 30 derniers messages de mon DM Slack et ignore les liens déjà envoyés.
Choisis 5 articles les plus utiles pour inspirer des propositions à des clients cloud
(postmortems, architectures de référence, solutions populaires). Varie les sources et les types.
Public : les SRE du Run Theodo, qui opèrent l'infra cloud de clients (Kubernetes, Terraform, CI/CD, monitoring, incidents, coûts, sécurité, montées de version).
Ouvre chaque article candidat et juge sa lisibilité : privilégie ceux qui sont structurés (titres, listes, chronologies, tableaux) et surtout ceux qui contiennent des schémas, diagrammes d'architecture ou graphiques. À pertinence égale, l'article avec schémas passe avant. Écarte les gros blocs de texte sans structure ni visuel, sauf si leur contenu est exceptionnel.
Garde uniquement les articles actionnables pour ce travail : ce qu'on peut appliquer, proposer ou vérifier chez un client.
Exclus ce qui concerne le métier du fournisseur plutôt que celui de l'opérateur : consommation énergétique ou refroidissement de datacenters, annonces de résultats ou de levées de fonds, partenariats, nouveaux datacenters ou régions sans impact pratique, produits sans lien avec l'infra, IA ou ML sans angle infra/ops.
Envoie-moi un DM Slack en français (le message principal), puis les sous-messages décrits plus bas. Dans le message principal, pour chaque article, ce format exact :

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

Sous-messages (après le message principal) :
Une fois le message principal posté, récupère son `ts` et poste un sous-message par article, en réponse dans le fil (thread) de ce message, dans le même ordre. Un seul article par sous-message. Relis l'article en entier avant de l'écrire.
Format exact :

*<emoji> Titre court de l'article*
*TLDR*
5-8 phrases : le contexte, ce qui s'est passé ou la solution retenue, les chiffres ou résultats clés, les limites ou pièges.
*Ce qu'on peut apporter à nos clients*
2-3 puces concrètes : quoi proposer ou vérifier chez un client, et pour quel bénéfice (moins de risque, moins de coût, moins de travail).
*Schéma*
```
schéma ASCII
```

Règles des sous-messages :
- Le TLDR est plus long que la description du message principal, mais reste centré sur ce que les SRE peuvent en faire chez un client, pas sur un résumé neutre de l'article.
- Le schéma résume le mécanisme de l'article (flux, architecture, chronologie d'incident ou avant/après), pas une liste de mots. Max 12 lignes et 60 caractères de large, caractères ASCII simples (`+ - | > v`), dans un bloc de code pour garder l'alignement dans Slack. Pas d'image ni de mermaid, Slack ne les rend pas.
- Pas de lien (déjà dans le message principal), pas d'intro, pas de conclusion, pas d'emoji hors du titre.
- Ne décris que ce que l'article dit réellement. Si un chiffre ou un détail n'y est pas, ne l'invente pas.
