# Directives — tour 1

## Ordre d'exécution

N2 livre et committe d'abord. N3 lit ensuite **les trois idées effectivement proposées par N2** et les évalue dans le même tour. Pas de démarchage, de dépense, de publication ni de code à ce stade. Chaque agent journalise et committe sa livraison selon le [protocole](../PROTOCOLE.md).

Au tour 0, les emplacements `N2_STRATEGIE` et `N3_PRODUIT` sont des fichiers ne contenant qu'un retour à la ligne. Chaque agent initialise uniquement son propre dossier selon le protocole, sans toucher celui de l'autre.

## N2 — trois idées de business classées

**Mission :** identifier et classer trois idées distinctes compatibles avec le [cap](00_CAP.md), sans présumer des contraintes encore inconnues du fondateur.

**Livrable unique :** `N2_STRATEGIE/TOUR_01_IDEES.md`.

**Pour chaque idée, fournir :**
1. Nom, cible précise, problème, offre livrée et canal d'acquisition principal.
2. Modèle de revenu répétable ou récurrent, prix et devise proposés comme **HYPOTHÈSE**, tâches et temps de service envisagés ; logique de marge, limites et risques principaux.
3. Au moins deux sources publiques consultables, avec URL et date de consultation : un indice de besoin ou d'achat et une offre comparable. Expliquer ce que chaque source démontre et ce qu'elle ne démontre pas ; une offre concurrente ne prouve pas ses ventes.
4. Notes de 0 à 10 pour les cinq critères du cap et moyenne sur 10 si les cinq notes sont renseignées. Expliquer brièvement chaque note et distinguer faits, estimations et inconnues.
5. Hypothèses de pays, de langue, de moyens de paiement, de budget et de disponibilité à confirmer ; ne pas présenter une hypothèse comme une contrainte réelle.

**Critère de réussite :** trois idées classées de la plus prometteuse à la moins prometteuse, avec les cinq éléments ci-dessus pour chacune et une justification du classement. Si une source ou une note manque, indiquer `ND`, ne pas calculer de score complet, rendre le classement provisoire et signaler le livrable comme partiel. Une idée n'est pas validée par ce classement.

## N3 — faisabilité et coût des trois idées de N2

**Mission :** comparer techniquement les trois idées du livrable de N2, sans choisir le business à la place de N1 ni développer le produit.

**Livrable unique :** `N3_PRODUIT/TOUR_01_FAISABILITE.md`.

**Pour chacune des trois idées, en reprenant son nom exact :**
1. Décrire le parcours minimal de vente et de livraison, les composants indispensables et ce qui est explicitement exclu du MVP.
2. Estimer le délai en jours ouvrés et le temps requis du fondateur ; préciser les hypothèses et conclure `faisable en deux semaines`, `non faisable` ou `à confirmer`, avec raison.
3. Détailler coûts initiaux, mensuels et variables par client ou transaction : hébergement, outils nécessaires et paiement. Donner devise, limites des offres gratuites, hypothèses d'usage, URL et date des tarifs vérifiés. Un coût inconnu est `ND`, pas zéro ; ne pas totaliser des devises différentes sans taux vérifié.
4. Signaler dépendances, risques de sécurité, éligibilité et disponibilité des moyens d'encaissement selon les pays ; si le pays ou le compte est inconnu, le marquer `à confirmer`.
5. Donner un verdict comparatif et les points à arbitrer par N1 ; indiquer les informations et autorisations nécessaires au fondateur.

**Critère de réussite :** trois évaluations comparables, chacune avec périmètre, délai, coûts par catégorie et verdict motivé. Les faits non vérifiés restent `ND` ; les prévisions motivées sont des **HYPOTHÈSES**. Une inconnue critique empêche une confirmation définitive. Si N2 n'a pas encore livré, attendre. Si N2 livre moins de trois idées ou est bloqué, évaluer seulement les idées disponibles et signaler le résultat partiel ou bloqué : ne pas inventer les autres.

## BESOINS DU FONDATEUR HUMAIN

Répondre aux questions du [tableau de bord](TABLEAU_DE_BORD.md), sans communiquer de secrets. La recherche sur sources publiques peut démarrer avec des hypothèses identifiées ; aucun engagement externe ne doit être pris sans autorisation.
