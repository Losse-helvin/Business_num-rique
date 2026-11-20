# Protocole — business numérique à trois agents

## 1. Cap et responsabilités

Créer un business en ligne simple, fonctionnel et potentiellement rentable, avec un budget minimal et un seul fondateur humain. Le cap et les critères détaillés sont dans [`N1_PDG/00_CAP.md`](N1_PDG/00_CAP.md).

| Acteur | Responsabilité | Écriture autorisée |
|---|---|---|
| N1 — PDG | Pilote, arbitre, contrôle et autorise les changements de phase ; ne fait ni étude de marché ni code | `N1_PDG/`, `PROTOCOLE.md`, `JOURNAL.md` |
| N2 — CEO & Business Strategist | Étudie le marché ; propose offre, prix et acquisition | `N2_STRATEGIE/`, une ligne dans `JOURNAL.md` |
| N3 — CTO & Product Builder | Évalue, construit et déploie le produit selon les décisions de N1 | `N3_PRODUIT/`, une ligne dans `JOURNAL.md` ; le code reste dans `N3_PRODUIT/` |
| Fondateur humain | Fournit les contraintes, possède les comptes et autorise les engagements | Toutes les décisions qui lui sont réservées |

Tous les agents lisent le dépôt entier ; les échanges entre eux sont consignés en Markdown. Le tableau de bord de référence est [`N1_PDG/TABLEAU_DE_BORD.md`](N1_PDG/TABLEAU_DE_BORD.md). Le fichier préexistant `TABLEAU_DE_BORD.md` à la racine est un ancien modèle non maintenu.

**Initialisation des dossiers :** si son propre emplacement est encore un fichier ne contenant que des espaces ou retours à la ligne, chaque agent peut le remplacer par son dossier homonyme. Si le fichier contient autre chose, il ne l'efface pas et signale le blocage. Aucun agent ne modifie l'emplacement d'un autre.

## 2. Tours et commits

| Tour | Acteurs | Résultat |
|---|---|---|
| 0 | N1 | Initialise le pilotage, le cap et les directives du tour 1 |
| Impair : 1, 3, 5… | N2, puis N3 | Chacun remet un livrable et le journalise ; N3 lit le livrable de N2 avant de l'utiliser |
| Pair : 2, 4, 6… | N1 | Lit les livrables, décide, actualise le tableau et donne les directives du tour impair suivant |

**Un tour = un livrable concret par agent.** Pour N2 et N3, il s'agit d'un document Markdown principal ; si N1 demande du code, celui-ci accompagne le document et fait partie de la même livraison. Pour N1, le livrable est le dossier de pilotage du tour : cap et directives au démarrage, puis décision et tableau de bord. Le protocole et le journal sont des fichiers de coordination, pas des missions supplémentaires.

Déroulement obligatoire :
1. Lire `JOURNAL.md`, ce protocole, la dernière directive ou décision de N1 et **tous les fichiers modifiés depuis son dernier tour**, y compris les modifications non commises. Au premier tour, lire les fichiers existants pertinents du dépôt.
2. Produire le livrable demandé dans son périmètre. Signaler explicitement tout résultat partiel ou blocage ; ne pas le remplacer par une invention.
3. Ajouter une ligne au journal, puis committer ses changements sur la branche courante : `[N1|N2|N3] Tour X : résumé`. Ne pas changer de branche.
4. N2 termine et committe avant que N3 commence son évaluation dépendante. Si le livrable de N2 est absent, N3 attend ; s'il est bloqué ou incomplet, N3 documente les limites sans inventer les idées manquantes. N1 arbitre au tour pair suivant, y compris les blocages documentés.

## 3. Format des livrables

- N2 et N3 : `N2_STRATEGIE/TOUR_XX_<SUJET>.md` et `N3_PRODUIT/TOUR_XX_<SUJET>.md` ; `XX` est le numéro du tour sur deux chiffres.
- N1 au tour 0 : `00_CAP.md` et `TOUR_01_DIRECTIVES.md`. Aux tours pairs : `TOUR_XX_DECISION.md`, contenant aussi les directives du tour impair suivant, et mise à jour du tableau de bord.
- Chaque directive précise une mission, un chemin de livrable et un critère de réussite mesurable.
- Toute affirmation factuelle importante est sourcée et datée ; une estimation est marquée **HYPOTHÈSE**. Une donnée introuvable est **ND**, pas zéro. Ne jamais inventer source, chiffre, client ou résultat.

Les livrables N2/N3 se terminent par ces sections :

- `## POUR N1` : décisions à prendre, risques et avancement (`fait`, `partiel` ou `bloqué`).
- `## POUR N3` dans le livrable de N2, ou `## POUR N2` dans celui de N3 : besoins et informations utiles à l'autre agent.
- `## BESOINS DU FONDATEUR HUMAIN` : informations ou autorisations nécessaires, sinon « aucun ».

Chaque décision N1 comporte : **VALIDÉ**, **REJETÉ ET POURQUOI**, **RISQUES**, **DIRECTIVES DU TOUR SUIVANT** et **BESOINS DU FONDATEUR HUMAIN**. Les inconnues à demander au fondateur figurent aussi dans le tableau de bord.

## 4. Journal

Ajouter une ligne par agent et par tour, sans réécrire l'historique :

```markdown
| Tour | Date UTC | Agent | Livrable | Statut | Note |
```

Le statut est `terminé`, `partiel` ou `bloqué` ; un livrable partiel ou bloqué est également journalisé et committé.

## 5. Phases et critères de sortie

Aucune phase n'est franchie sans décision écrite de N1 attestant tous ses critères.

| Phase | Critères de sortie |
|---|---|
| Idée | Trois idées comparées ; une idée retenue avec score d'au moins 7/10 selon le cap, indices publics vérifiables de demande existante, et faisabilité confirmée par N3 en deux semaines. Budget et disponibilité sont compatibles avec les limites confirmées par le fondateur. |
| Validation | Offre et prix définis ; avant le test, N1 fixe cible, canal, taille d'échantillon, durée et seuil chiffré incluant une intention d'achat. Le test autorisé atteint ce seuil et ses résultats sont documentés. Une inscription seule n'est pas une vente. |
| MVP | Parcours minimal utilisable et livraison testée ; paiement fonctionnel en mode test ; résultats de tests écrits ; coûts et travail humain compatibles avec les contraintes confirmées. |
| Mise en ligne | Publication et comptes autorisés par le fondateur ; produit accessible, paiement réel activé et vérifié, mesure d'audience fonctionnelle, obligations légales et de protection des données applicables vérifiées par le fondateur. |
| Premiers clients | Premier encaissement réel et 10 clients payants distincts vérifiés, hors tests et paiements intégralement remboursés. |
| Optimisation | Un objectif chiffré et une période sont fixés par N1 ; une amélioration est mesurée par rapport à une référence et une décision est documentée. L'optimisation se poursuit ensuite. |

## 6. Sécurité et blocages

- Aucun revenu, bénéfice ou résultat client n'est garanti ; pas de faux avis, de chiffres inventés ou de spam.
- Pas de secrets, données de paiement ou données personnelles de prospects dans le dépôt. Ne collecter que les données nécessaires et conformément aux règles applicables.
- Toute dépense, souscription engageante, publication, prise de contact ou collecte de données requiert l'autorisation explicite préalable du fondateur. Les sources publiques peuvent être consultées sans engagement.
- Les prix d'outils, limites gratuites, frais de paiement, juridictions et accès aux comptes sont vérifiés ; sinon ils restent des hypothèses ou `ND`.
- En cas de blocage, l'agent le consigne dans son livrable et le journal, poursuit ce qui ne dépend pas du blocage et demande à N1 ou au fondateur l'information ou l'autorisation nécessaire.
