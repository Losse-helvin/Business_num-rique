# N3 — Tour 1 : Faisabilité technique et coûts des trois idées

**Auteur :** N3 (CTO & Product Builder) · **Date :** 2026-11-20 UTC · **Directive :** [`N1_PDG/TOUR_01_DIRECTIVES.md`](../N1_PDG/TOUR_01_DIRECTIVES.md)
**Entrée :** [`N2_STRATEGIE/TOUR_01_IDEES.md`](../N2_STRATEGIE/TOUR_01_IDEES.md)
**Statut :** fait — évaluation technique comparative des trois idées de N2, sans choix de business ni développement.

**Conventions.** **FAIT** = vérifié sur source publique consultée le 2026-11-20. **HYPOTHÈSE** = estimation technique de N3. **ND** = donnée non disponible. **à confirmer** = dépend d'une information ou d'un compte du fondateur.

---

## 0. Synthèse comparative

| Critère | Idée A : Pack Reels | Idée B : Veille AO Propreté | Idée C : Kit Micro-Entreprise |
|---|---|---|---|
| **Complexité technique** | Nulle (aucun code) | Moyenne (script API + e-mailing + paiement) | Faible (tableur + PDF + plateforme) |
| **Délai MVP (jours ouvrés)** | **2 à 4 jours** (HYPOTHÈSE) | **6 à 9 jours** (HYPOTHÈSE) | **3 à 5 jours** (HYPOTHÈSE) |
| **Faisabilité en 2 semaines** | **à confirmer** (dépend compétence vidéo + compte ComeUp) | **à confirmer** (dépend prestataire paiement B2B) | **à confirmer** (dépend éligibilité plateforme/fisc) |
| **Coût fixe lancement** | 0 € (hors matériel existant) | 0 $ / 0 € (offres gratuites) | 0 $ / 0 € |
| **Coût mensuel min.** | 0 € (ou 12 € HT ComeUp Plus) | 0 $ (Brevo Free ≤ 300/j) | 0 $ (Gumroad) |
| **Encaissement si Madagascar** | **Plausible** (ComeUp → Hyperwallet, frais MG **ND**) | **Bloqué en direct** (Stripe vendeur non dispo ; Gumroad possible en contournement mais peu B2B) | **Plausible via Gumroad** (virement MGA dispo) ; **Bloqué sur Etsy/PayPal** |

---

## 1. Idée A — « Pack Reels »

### 1.1 Parcours minimal, composants et exclusions MVP
- **Parcours minimal de vente et livraison :**
  1. Le client achète le service sur **ComeUp** (vidéo test 19 € ou pack 8 vidéos 149 €).
  2. Le client dépose ses rushes via un lien de transfert (messagerie ComeUp, Google Drive ou WeTransfer gratuit).
  3. Le fondateur monte la vidéo (coupes, format 9:16), génère/corrige les sous-titres, exporte en MP4.
  4. Livraison via ComeUp ; le client valide la commande (ce qui débloque les gains).
- **Composants indispensables :** compte vendeur ComeUp + fiche service + 2-3 vidéos d'exemple libres de droits + logiciel de montage/sous-titrage (ex. CapCut Desktop ou DaVinci Resolve + Whisper en local) + stockage cloud gratuit (Google Drive 15 Go).
- **Exclus explicitement du MVP :** site vitrine dédié, système de paiement propre, automatisation de dépôt/livraison, CRM, abonnement hors plateforme.

### 1.2 Délai et temps fondateur
- **Délai estimé :** **2 à 4 jours ouvrés** (HYPOTHÈSE) : création compte/identité (1 j), production de 2-3 exemples (1-2 j), rédaction et soumission de la fiche ComeUp + délai de modération ComeUp (**ND**).
- **Temps requis du fondateur :** 6 à 10 h pour le setup ; puis ~4 h 15 par pack Essentiel (HYPOTHÈSE).
- **Verdict 2 semaines :** **à confirmer** — techniquement faisable en < 5 jours ouvrés, mais conditionné à la compétence vidéo du fondateur et à la validation du compte vendeur ComeUp.

### 1.3 Coûts (vérifiés le 2026-11-20)
- **Initiaux :** 0 € (HYPOTHÈSE : le fondateur possède déjà un ordinateur et une connexion internet capables d'uploader des vidéos HD).
- **Mensuels :**
  - ComeUp Standard : **0 €** (commission 20 % HT).
  - Option ComeUp Plus Standard : **12 € HT/mois** (ramène la commission à 1 € HT/commande ; rentable dès 2 commandes à 50 € HT ou 1 à 100 € HT) — [FreelanceMention, 2026-10-09](https://freelancemention.fr/blog/alternative-comeup/).
  - Outils montage : CapCut gratuit ou DaVinci Resolve gratuit = **0 €** (limites : certaines fonctions IA/export avancées de CapCut sont passées en Pro ; **à vérifier** lors de l'installation).
- **Variables par transaction :**
  - Commission vendeur ComeUp : **20 % HT** sans abonnement, ou **1 € HT/commande** avec Plus ([FreelanceMention](https://freelancemention.fr/blog/alternative-comeup/)).
  - Frais acheteur (inclus dans le prix affiché selon source) : **8,5 % HT** ([Web&Seo, 2026-10-30](https://www.webandseo.fr/fiverr-vs-5euros/)).
  - Frais de retrait Hyperwallet vers banque malgache : **ND** (gratuit vers carte, 0,50 € SEPA selon support ComeUp ; tarif MGA/SWIFT non vérifié).

### 1.4 Dépendances, risques et encaissement
- **Dépendances :** modération ComeUp, règles CGU (interdiction probable de contourner la plateforme), disponibilité de CapCut/Whisper.
- **Sécurité / Données :** rushes clients à supprimer après validation de commande (minimisation des données). Droits à l'image sur le portfolio.
- **Encaissement :** **à confirmer** — Hyperwallet est utilisé par ComeUp, mais les frais, seuils et banques éligibles à Madagascar restent **à confirmer** par le fondateur.

---

## 2. Idée B — « Veille AO Propreté »

### 2.1 Parcours minimal, composants et exclusions MVP
- **Parcours minimal de vente et livraison :**
  1. Un script automatisé interroge l'API BOAMP chaque semaine, filtre les avis (codes CPV nettoyage, département/région, date limite) et génère un brouillon.
  2. Le fondateur relit, résume en 3 lignes par avis et colle le contenu dans une campagne e-mail.
  3. Le client s'abonne via une page de paiement simple (lien de paiement récurrent) et reçoit l'e-mail chaque lundi.
- **Composants indispensables :** script Python/Node (exécuté via GitHub Actions gratuit), outil d'e-mailing (Brevo Free), page de présentation statique (GitHub Pages / Cloudflare Pages), lien de paiement récurrent.
- **Exclus explicitement du MVP :** espace membre/login, base de données complexe, tableau de bord client, filtrage personnalisé par client, aide à la rédaction des réponses.

### 2.2 Délai et temps fondateur
- **Délai estimé :** **6 à 9 jours ouvrés** (HYPOTHÈSE) : exploration API BOAMP + script de filtrage (2-3 j), page statique + mentions légales (1-2 j), configuration Brevo + paiement + tests bout en bout (2-3 j), intégration retours (1 j).
- **Temps requis du fondateur :** 3 à 5 h pour valider les critères de filtrage et configurer les comptes (paiement, Brevo) ; puis 2-3 h/semaine de relecture.
- **Verdict 2 semaines :** **à confirmer** — faisable techniquement en ≤ 9 jours ouvrés, mais **bloqué sur le paiement par carte direct** si le fondateur est à Madagascar.

### 2.3 Coûts (vérifiés le 2026-11-20)
- **Initiaux :** **0 €** (API BOAMP gratuite, Licence Ouverte 2.0 — [data.gouv.fr](https://www.data.gouv.fr/dataservices/api-bulletin-officiel-des-annonces-des-marches-publics-boamp) ; hébergement statique et GitHub Actions gratuits dans les limites publiques).
- **Mensuels :**
  - Brevo Free : **0 $** jusqu'à **300 e-mails/jour** (avec logo Brevo ; plan Starter à 9 $/mois si volume supérieur ou retrait du logo) — [EmailSoftwareInsights, 2026-11-11](https://www.emailsoftwareinsights.com/reviews/brevo/pricing/free-plan/).
- **Variables par transaction :** **ND** (dépend du prestataire de paiement éligible au pays du fondateur).

### 2.4 Dépendances, risques et encaissement
- **Dépendances :** disponibilité et schéma de l'API BOAMP, délivrabilité e-mail (SPF/DKIM requis, nécessite idéalement un nom de domaine à ~10-15 €/an, **HYPOTHÈSE**).
- **Sécurité / RGPD :** prospection B2B encadrée (opt-out obligatoire, source des données publiques à mentionner).
- **Encaissement :** **à confirmer (risque élevé)** — Stripe en tant que vendeur direct n'est pas disponible à Madagascar (Stripe Global Payouts supporte Madagascar uniquement en *destinataire* depuis jan 2026 — [Stripe Docs](https://docs.stripe.com/changelog/clover/2026-01-28/cross-border-payouts-new-countries)). Sans entité/compte dans un pays éligible, l'abonnement B2B par carte directe est **bloqué** (ou nécessite un intermédiaire type Gumroad/Lemon Squeezy, moins adapté au B2B).

---

## 3. Idée C — « Kit Micro-Entreprise »

### 3.1 Parcours minimal, composants et exclusions MVP
- **Parcours minimal de vente et livraison :**
  1. Le client trouve la fiche produit (Gumroad ou Payhip) et paie par carte.
  2. La plateforme encaisse et envoie automatiquement le lien de téléchargement (fichier `.xlsx` / lien Google Sheets + guide `.pdf`).
- **Composants indispensables :** tableur (Excel/Google Sheets) testé avec formules + guide PDF + compte vendeur sur plateforme de produits numériques.
- **Exclus explicitement du MVP :** application web, connexion API URSSAF, mises à jour automatiques en ligne, support par chat en direct.

### 3.2 Délai et temps fondateur
- **Délai estimé :** **3 à 5 jours ouvrés** (HYPOTHÈSE) : conception et tests des formules du tableur (2-3 j), rédaction guide PDF (1 j), mise en ligne fiche produit et test d'achat (1 j).
- **Temps requis du fondateur :** 4 à 6 h pour création/relecture et ouverture du compte plateforme.
- **Verdict 2 semaines :** **à confirmer** — techniquement très rapide, mais soumis à la vérification des taux URSSAF/TVA officiels et à l'acceptation du compte vendeur.

### 3.3 Coûts (vérifiés le 2026-11-20)
- **Initiaux :** **0 $** (création tableur via Google Sheets/LibreOffice gratuit).
- **Mensuels :** **0 $** sur Gumroad ou Payhip Free.
- **Variables par transaction :**
  - **Gumroad :** **10 % + 0,50 $** par vente directe (30 % si vente via Gumroad Discover) + frais de traitement carte/PayPal — [Latuos, 2026-09-14](https://latuos.com/gumroad-fees/).
  - **Payhip Free :** **5 %** par vente + frais Stripe/PayPal ([Sellfy, 2026-05-07](https://sellfy.com/blog/gumroad-vs-payhip/)). *Note : Payhip nécessite un processeur connecté (Stripe/PayPal), donc inéligible si Madagascar sans compte tiers.*

### 3.4 Dépendances, risques et encaissement
- **Dépendances :** exactitude des seuils fiscaux/sociaux français (risque de responsabilité si erreur de calcul ; clause de non-conseil comptable indispensable).
- **Encaissement :** **à confirmer** — **Gumroad** supporte les virements bancaires vers **Madagascar en MGA** (seuil minimum de retrait : **132 300 MGA** — [Gumroad Help Center](https://gumroad.com/help/article/13-getting-paid)). Etsy Payments et PayPal réception restent indisponibles à Madagascar (confirmé par N2).

---

## 4. Verdict comparatif N3

1. **Idée A (Pack Reels)** est la plus simple techniquement (0 code, 2-4 jours) et évite le blocage d'encaissement direct par carte grâce à ComeUp, **si et seulement si** le fondateur sait (ou veut) monter des vidéos courtes.
2. **Idée C (Kit Micro-Entreprise)** est la plus rapide à packager (3-5 jours) et encaissable depuis Madagascar via **Gumroad** (virement MGA), mais ses frais unitaires (10 % + 0,50 $) et sa faible récurrence confirment le rang 3.
3. **Idée B (Veille AO Propreté)** est faisable en < 2 semaines côté code (6-9 jours), mais **risque un blocage d'encaissement B2B** si le fondateur n'a pas accès à Stripe/un PSP équivalent.

---

## POUR N1

- **Décisions à prendre :**
  1. Arbitrer entre **A (Pack Reels)** et **B (Veille AO Propreté)** dès réception des réponses du fondateur (compétence vidéo et pays/moyen d'encaissement).
  2. Si **B** est envisagée et que le fondateur est à Madagascar sans société/compte Stripe à l'étranger, demander une solution d'encaissement (ex. Merchant of Record type Gumroad/Lemon Squeezy) ou écarter B pour la phase 1.
- **Risques :** les trois verdicts restent `à confirmer` tant que le pays d'encaissement et la compétence vidéo ne sont pas confirmés.
- **Avancement :** `fait`.

## POUR N2

- Pour **Pack Reels**, les frais acheteur ComeUp sont confirmés à **8,5 % HT** (inclus dans le prix affiché) et la commission vendeur à **20 % HT** (ou 1 € HT avec Plus à 12 € HT/mois). Tu peux intégrer ces chiffres dans ton modèle de marge au tour 3 si A est retenue.
- Pour **Kit Micro-Entreprise**, **Gumroad** est la piste viable pour Madagascar (virement MGA, 10 % + 0,50 $).

## BESOINS DU FONDATEUR HUMAIN

1. Confirmer le **pays de résidence et d'encaissement** (et si vous disposez d'un compte bancaire pouvant recevoir des virements internationaux / Hyperwallet / Gumroad).
2. Confirmer votre **compétence ou appétence pour le montage vidéo court** (pour l'Idée A).
3. Confirmer votre **disponibilité hebdomadaire** et votre **budget maximal** (0 € possible pour A et C ; ~10-15 €/an recommandé pour un domaine si B).
