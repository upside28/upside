# Règles de travail communes — UPSIDE

## Portée et priorité métier

Ces règles s'appliquent à Codex et Claude Code sur l'ensemble du dépôt. Ce document est leur référence commune ; `AGENTS.md` et `CLAUDE.md` sont uniquement des points d'entrée. Les deux outils doivent pouvoir intervenir sur le même dépôt sans créer de conventions concurrentes. Toute évolution des règles partagées doit être centralisée ici.

UPSIDE est d'abord un cabinet de conseil immobilier. Le besoin métier, les usages et la fiabilité des résultats priment sur la technologie. Les choix techniques doivent servir un besoin explicite.

## Comprendre avant de modifier

- Lire et comprendre l'existant avant toute modification : fichiers concernés, documentation disponible, usages, dépendances et règles métier.
- GitHub est la source canonique du code. Dropbox contient la documentation, les templates et les archives métier ; ces éléments peuvent éclairer une modification, sans constituer une source concurrente du code.
- Préserver les règles métier existantes tant qu'elles n'ont pas été explicitement arbitrées.
- En cas de divergence entre Excel, HTML et un guide, la signaler avant de choisir une interprétation. Ne pas trancher implicitement ; obtenir un arbitrage explicite si le choix change une règle métier.
- Distinguer clairement les faits observés, les hypothèses et les points non vérifiés, dans les échanges comme dans la documentation.

## Délimiter chaque modification

- Ne jamais modifier directement `main`. Vérifier la branche et l'état du working tree avant d'intervenir, puis travailler sur une branche dédiée. Préserver les modifications déjà présentes.
- Une modification doit avoir un périmètre limité, des critères d'acceptation explicites et des tests adaptés. Définir ces éléments avant de modifier les fichiers ; éviter les refontes et corrections annexes.
- Vérifier les critères d'acceptation après le changement. Les tests peuvent être manuels ou automatisés selon le périmètre ; ne pas créer d'infrastructure de test sans besoin ni instruction correspondante.
- Prévoir un rollback avant le changement : identifier l'état de référence et la manière de revenir en arrière sans écraser le travail existant. Définir aussi les vérifications à effectuer après le changement et après un éventuel rollback.
- Documenter les changements significatifs : besoin traité, périmètre, décisions métier, comportement obtenu, vérifications réalisées et limites restantes.

## Respecter les limites d'intervention

- **Ce dépôt est public.** Ne jamais y ajouter de documents internes ou confidentiels, données clients, exports métier non destinés à publication, secrets, credentials, prompts/Skills internes, templates propriétaires non destinés à publication ou détails de sécurité non publics. Les éléments professionnels internes qui doivent être versionnés doivent vivre dans un espace privé approprié.
- Ne pas modifier la production, Supabase, les workflows, les secrets ou les données clients sans instruction explicite couvrant l'intervention concernée.
- Ne jamais écrire de secret, token, mot de passe ou donnée client dans Git, y compris dans le code, les exemples, les tests et la documentation. Utiliser des valeurs fictives pour les exemples.
- Lorsqu’un problème hors périmètre est découvert, le signaler sans le corriger au passage. Son traitement doit faire l’objet d’un périmètre explicitement validé.

## Rendre compte avec exactitude

- Ne jamais présenter comme testé ou déployé ce qui ne l'est pas.
- Indiquer précisément les vérifications exécutées, leurs résultats, les vérifications non effectuées et les points restant à confirmer.
- Distinguer une modification locale, un commit, une publication sur GitHub et un déploiement effectif. Une étape ne prouve pas l'exécution de la suivante.
- Lorsqu'un déploiement est explicitement demandé, effectuer les vérifications prévues après déploiement et signaler toute impossibilité de les réaliser.

## Outils actuels

- Les applications sont principalement des pages HTML/JavaScript statiques ; comprendre l'organisation de chaque outil avant de proposer un changement de structure.
- GitHub Pages est utilisé pour l'hébergement. Vérifier le mécanisme de publication concerné avant toute intervention susceptible d'affecter le site publié.
- Supabase est utilisé selon les outils ; vérifier les dépendances du périmètre concerné et respecter les limites d'intervention ci-dessus.
- Excel sert souvent de référence de conception métier. Consulter les éléments disponibles et signaler les divergences avec le HTML ou les guides avant de choisir.
