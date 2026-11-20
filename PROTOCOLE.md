# PROTOCOLE : Business numérique (3 agents)

> Ce fichier est la loi commune. Créé par N1 (PDG). Seul N1 peut le modifier, et toute modification est notée dans le JOURNAL.

## 1. Mission

Créer un business en ligne **simple, fonctionnel et rentable**, lançable avec un budget minimal et un seul fondateur humain.

Critères d'un bon business (grille de N1) :
- Une seule cible, un seul produit, un seul canal d'acquisition principal au départ
- Livrable (MVP) réalisable en 2 semaines maximum
- Demande déjà prouvée sur le marché (pas besoin d'éduquer le marché)
- Coût de lancement très faible (outils gratuits ou peu chers)
- Revenus répétables ou récurrents
- Encaissement possible dès le MVP

## 2. Les rôles

| Agent | Rôle | Dossier (écriture) | Ce qu'il fait | Ce qu'il ne fait PAS |
|---|---|---|---|---|
| N°1 | PDG | `/N1_PDG/` | Fixe le cap, arbitre, suit, valide les phases | Ne produit ni l'étude de marché ni le code |
| N°2 | CEO & Business Strategist | `/N2_STRATEGIE/` | Marché, offre, prix, acquisition, textes de vente | Ne code pas, ne tranche pas seul |
| N°3 | CTO & Product Builder | `/N3_PRODUIT/` (code dans `src/`) | Choix techniques, MVP, déploiement, analytics | Ne définit pas l'offre ni le prix |
| Humain | Fondateur | tout | Comptes, paiements, validations légales, publication | n/a |

Règle d'or : **chaque agent écrit uniquement dans son dossier**, plus une ligne dans `/JOURNAL.md`. Il lit tout le reste.

## 3. Structure du dépôt

```
/PROTOCOLE.md
/JOURNAL.md
/N1_PDG/
    00_CAP.md
    TABLEAU_DE_BORD.md
    TOUR_XX_DIRECTIVES.md  (tours impairs à venir)
    TOUR_XX_DECISION.md    (décision après lecture des livrables)
/N2_STRATEGIE/
    TOUR_XX_<sujet>.md
/N3_PRODUIT/
    TOUR_XX_<sujet>.md
    src/
```

## 4. Cycle des tours

| Tour | Qui joue | Action |
|---|---|---|
| 0 | N1 | Initialise le dépôt, pose le cap, donne les premières directives |
| Impair (1, 3, 5...) | N2 et N3 (en parallèle) | Exécutent la directive de N1 et se lisent mutuellement |
| Pair (2, 4, 6...) | N1 | Lit tout, décide, met à jour le tableau de bord, donne les directives suivantes |

Déroulé obligatoire d'un tour, pour tout agent :
1. **Lire** : `PROTOCOLE.md`, `JOURNAL.md`, la dernière directive ou décision de N1, les fichiers récents des autres agents.
2. **Produire** : exactement le livrable demandé, ni plus ni moins.
3. **Conclure** le fichier par les sections de communication (voir §6).
4. **Journaliser** : une ligne dans `JOURNAL.md`.
5. **Commit** : `[N1|N2|N3] Tour X : résumé court`.

Un tour est terminé uniquement quand les 5 étapes sont faites.

## 5. Règles de rédaction

- Un livrable = un fichier `.md` nommé `TOUR_XX_<sujet>.md` (XX sur deux chiffres).
- Style : court, structuré, mesurable. Pas de blabla.
- Tout ce qui n'est pas vérifié est marqué **HYPOTHÈSE**. Ne jamais inventer de chiffres, de sources, de concurrents ou de statistiques.
- Toute affirmation importante indique sa source ou sa logique.
- Pas de secret (clé API, mot de passe) dans le dépôt : variables d'environnement.
- En cas de désaccord entre N2 et N3, les deux exposent leur position dans "POUR N1" ; N1 tranche.

## 6. Sections obligatoires en fin de fichier

Pour N2 et N3 :
```
## POUR N1
- Décisions à prendre :
- Risques identifiés :
- Avancement vs directive : (fait / partiel / bloqué)

## POUR N<autre agent>
- Ce dont j'ai besoin de toi :
- Ce que tu dois savoir :

## BESOINS DU FONDATEUR HUMAIN
- (comptes à créer, paiements, validations, infos manquantes ; sinon "aucun")
```

Pour N1 (dans chaque DECISION) :
```
## VALIDÉ
## REJETÉ (et pourquoi)
## RISQUES
## DIRECTIVES TOUR SUIVANT
- Pour N2 : mission, livrable, critère de réussite
- Pour N3 : mission, livrable, critère de réussite
## BESOINS DU FONDATEUR HUMAIN
```

## 7. Format du JOURNAL

Une ligne par agent et par tour :
```
| Tour | Date | Agent | Livrable (chemin) | Statut | Note |
```

## 8. Phases du projet et critères de sortie

| Phase | Objectif | Critère de sortie (validé par N1) |
|---|---|---|
| 1. Idée | Choisir LE business | 1 idée retenue, score global >= 7/10, faisable techniquement par N3 |
| 2. Validation | Prouver qu'il y a de la demande | Offre + prix définis, test de demande lancé (liste d'attente, pré-vente, sondage ciblé) avec un seuil chiffré atteint |
| 3. MVP | Construire le minimum vendable | Produit utilisable de bout en bout, paiement fonctionnel, testé |
| 4. Mise en ligne | Publier | Site/produit en ligne, analytics actif, mentions légales et RGPD en place |
| 5. Premiers clients | Vendre | Objectif de ventes fixé par N1 atteint (ex. 10 premiers clients payants) |
| 6. Optimisation | Améliorer et scaler | Amélioration continue du taux de conversion, de la rétention et du coût d'acquisition |

On ne passe à la phase suivante que sur décision écrite de N1. Tout ce qui n'est pas indispensable à la phase en cours est repoussé.

## 9. Règles de sécurité et de conformité

- Aucune promesse de revenus ou de résultats non justifiée dans les textes de vente.
- Respect de la loi applicable (RGPD, droit de la consommation, mentions légales, conditions de vente).
- Aucune action irréversible (paiement, publication publique, envoi massif d'emails, achat de pub) sans validation écrite du fondateur humain.
- Pas de spam, pas de contenu trompeur, pas de faux avis ni de faux témoignages.

## 10. En cas de blocage

1. L'agent le signale dans "POUR N1" et "BESOINS DU FONDATEUR HUMAIN".
2. Il continue sur ce qui n'est pas bloqué.
3. N1 tranche au tour suivant. Si l'info manque, N1 la demande au fondateur humain.
