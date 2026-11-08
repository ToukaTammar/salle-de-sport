# TP1 — Cadrage du projet

**Équipe :** [noms des membres du groupe]
**Sujet 5 — Salle de sport : abonnements et accès** (dossier du projet : `salle-de-sport/`)

---

## 0. Référentiel de la demande client

Pour assurer la traçabilité, chaque phrase de la demande est numérotée. Tout ce qui n'apparaît pas ci-dessous est traité comme **hypothèse**, **point ouvert** ou **proposition à rejeter**.

| N° | Phrase de la demande |
|----|----------------------|
| S0 | Contexte : salle de sport de quartier, environ 400 adhérents, 2 agents d'accueil, 3 coachs et un gérant. |
| S1 | « Notre salle de sport veut moderniser sa gestion avec une application. » |
| S2 | « Les adhérents doivent pouvoir consulter leur abonnement et le renouveler, et ceux qui partent en voyage ne veulent pas perdre les jours payés. » |
| S3 | « À l'accueil, le système doit contrôler l'accès des adhérents. » |
| S4 | « Le gérant veut gérer les formules d'abonnement et suivre la fréquentation de la salle. » |
| S5 | « Un adhérent ne doit pas pouvoir entrer si son abonnement n'est pas valable. » |
| S6 | « Il ne faut pas non plus bloquer à la porte un bon client dont l'abonnement vient de finir. » |
| S7 | « Certains adhérents prêtent leur carte à des amis : il faut les sanctionner. » |
| S8 | « Les coachs demandent qu'on arrête les entrées bien avant la fermeture, pour ranger la salle. » |
| S9 | « L'accueil, lui, voudrait laisser entrer les adhérents jusqu'à la dernière minute. » |
| S10 | « L'application doit être moderne et agréable. » |

---

## 1. Vision

### Q1 — Problème métier

**Problème métier :** la salle ne dispose pas d'un moyen fiable et équitable de vérifier, au moment de l'entrée, si un adhérent a droit d'accéder à la salle, ni de permettre aux adhérents de suivre et prolonger leur abonnement (y compris lorsqu'ils s'absentent), ce qui expose la salle à des entrées indues, des refus injustes et un manque de visibilité sur la fréquentation.

**Phrase décrivant déjà une solution :** S1 — « Notre salle de sport veut moderniser sa gestion **avec une application** ». « Une application » est une solution possible, pas le problème métier. Le même type de dérive apparaît dans S10 (« moderne ») qui est un qualificatif de solution et non un besoin métier.

### Q2 — Parties prenantes

| Partie prenante | Statut | Intérêt / attente |
|---|---|---|
| Adhérents (~400) | Explicite (S0, S2) | Consulter et renouveler leur abonnement, ne pas perdre les jours payés lors d'un voyage, entrer sans blocage injustifié. |
| Agents d'accueil (2) | Explicite (S0, S3, S9) | Contrôler l'accès sans friction, pouvoir laisser entrer jusqu'à la dernière minute. |
| Coachs (3) | Explicite (S0, S8) | Arrêter les entrées bien avant la fermeture pour ranger la salle. |
| Gérant | Explicite (S0, S4) | Gérer les formules d'abonnement, suivre la fréquentation. |
| Propriétaire / direction (si distinct du gérant) | Non citée | Rentabilité, réduction de la fraude, image de la salle. |
| Adhérents qui prêtent leur carte et amis bénéficiaires | Citée indirectement (S7) | Concernés par la sanction ; ne sont pas des utilisateurs du système mais des personnes impactées. |
| Nouveaux adhérents / prospects | Non citée | Souscrire un premier abonnement (à valider : hors du périmètre explicite). |
| Prestataire informatique / maintenance (si existant) | Non citée | Exploitation, support, évolutions. |
| Autorité de protection des données personnelles | Non citée | Conformité : le système traitera des données personnelles (identité, présence). |

### Q3 — Objectifs (gabarit : verbe + indicateur + valeur actuelle → valeur cible + délai)

> Aucune valeur n'est inventée : toute valeur non fournie par le client est notée **[à valider]**.

- **OBJ-01 — Réduire** le nombre d'entrées effectuées avec un abonnement non valable ou avec la carte d'un autre adhérent de **[valeur actuelle à mesurer]** à **[valeur cible à valider]** d'ici **[délai à valider]**. *(S3, S5, S7)*
- **OBJ-02 — Augmenter** la proportion de renouvellements d'abonnement effectués directement par l'adhérent, sans passer par l'accueil, de **[valeur actuelle à mesurer]** à **[valeur cible à valider]** d'ici **[délai à valider]**. *(S2)*
- **OBJ-03 — Augmenter** la proportion des entrées enregistrées dans le système (base du suivi de fréquentation) de **[valeur actuelle à mesurer]** à **[valeur cible à valider]** d'ici **[délai à valider]**. *(S3, S4)*

### Q4 — Objectif le plus difficile à mesurer

Le plus difficile à mesurer est **« moderne et agréable »** (S10). Ces termes sont subjectifs : ce qui est agréable pour un adhérent peut ne pas l'être pour un agent d'accueil ou un coach. Il faudrait choisir un indicateur (taux de réussite d'un renouvellement lors d'un test utilisateur, temps pour effectuer une tâche, note de satisfaction sur une échelle) et fixer une valeur cible **avec le client**.

Autre notion difficile à mesurer : **« bon client »** (S6), qui n'a aucune définition (ancienneté ? régularité ? paiements à jour ?).

---

## 2. Périmètre

### Q5 — Tableau connu / inconnu

| Élément | Catégorie | Source (phrase de la demande) ou « à valider » |
|---|---|---|
| Un adhérent peut consulter son abonnement | Dans le périmètre | S2 |
| Un adhérent peut renouveler son abonnement | Dans le périmètre | S2 |
| Un adhérent qui part en voyage ne perd pas les jours payés | Dans le périmètre — **mécanisme à préciser** (voir PO-01) | S2 |
| Le système contrôle l'accès des adhérents à l'accueil | Dans le périmètre | S3 |
| L'entrée est refusée si l'abonnement n'est pas valable | Dans le périmètre — **définition de « valable » à préciser** | S5 |
| Un bon client dont l'abonnement vient de finir ne doit pas être bloqué | Dans le périmètre — **règle à préciser** (voir PO-03) | S6 |
| Le prêt de carte doit être sanctionné | Dans le périmètre — **détection et sanction à préciser** (voir PO-04) | S7 |
| Le gérant gère les formules d'abonnement | Dans le périmètre — « gérer » est ambigu (voir PO-02) | S4 |
| Le gérant suit la fréquentation de la salle | Dans le périmètre — **indicateurs à préciser** (voir PO-07) | S4 |
| L'application est moderne et agréable | Contrainte non fonctionnelle — **non mesurable en l'état** (voir PO-10) | S10 |
| Contexte de taille : ~400 adhérents, 2 agents d'accueil, 3 coachs, 1 gérant | Contrainte (dimensionnement) | S0 |
| Heure limite d'entrée : les coachs et l'accueil ont des attentes opposées | **Point ouvert** — conflit entre parties prenantes à arbitrer par le client (PO-05) | S8, S9 |
| Chaque adhérent possède une carte qui l'identifie à l'entrée (support : physique, QR code, numéro…) | **Hypothèse** (H-01) — voir PO-08 | « leur carte » (S7), nature non précisée |
| Les adhérents disposent d'un smartphone ou d'un ordinateur pour consulter et renouveler | **Hypothèse** (H-02) — voir PO-08 | À valider |
| Les données existantes des ~400 adhérents (abonnements) sont disponibles et à reprendre | **Hypothèse** (H-03) — voir PO-11 | À valider |
| L'accueil dispose du matériel nécessaire (poste, lecteur) pour contrôler les accès | **Hypothèse** (H-04) — voir PO-08 | À valider |
| PO-01 : Comment fonctionne la protection des jours payés en voyage (gel, prolongation, durée min/max, justificatif, qui valide) ? | **Point ouvert** | À valider (S2) |
| PO-02 : Que signifie « gérer les formules » (créer, modifier, supprimer, activer, désactiver, tarifs) ? Quelles formules existent ? | **Point ouvert** | À valider (S4) |
| PO-03 : Qu'est-ce qu'un « bon client » et combien de temps après la fin de l'abonnement l'accès reste-t-il toléré ? | **Point ouvert** | À valider (S6) |
| PO-04 : Comment détecter un prêt de carte et quelle sanction appliquer (avertissement, suspension, amende, exclusion), par qui ? | **Point ouvert** | À valider (S7) |
| PO-05 : Quelle heure limite d'entrée avant la fermeture ? Qui tranche entre coachs et accueil ? Dérogation possible ? | **Point ouvert** | À valider (S8, S9) |
| PO-06 : Le renouvellement implique-t-il un paiement dans l'application, ou seulement une demande/déclaration payée à l'accueil ? | **Point ouvert** | À valider (S2) |
| PO-07 : Quels indicateurs de fréquentation (par jour, par heure, par adhérent), sur quelle période, sous quelle forme ? Faut-il enregistrer seulement les entrées ou aussi les sorties ? *(précision ajoutée après l'analyse IA, voir Q12)* | **Point ouvert** | À valider (S4) |
| PO-08 : Sur quels supports l'application doit-elle fonctionner (téléphone, ordinateur, les deux) ? Comment l'accès est-il contrôlé (agent qui vérifie, borne, tourniquet) ? | **Point ouvert** | À valider (S1, S3) |
| PO-09 : Comment les adhérents s'identifient-ils dans l'application ? Qui crée leurs comptes ? | **Point ouvert** | À valider |
| PO-10 : Que signifie « moderne et agréable » de façon vérifiable ? | **Point ouvert** | À valider (S10) |
| PO-11 : L'inscription d'un nouvel adhérent et la reprise des données existantes sont-elles dans le périmètre ? | **Point ouvert** | À valider (S2) |
| PO-12 : Quels droits ont les agents d'accueil et les coachs dans le système ? Les coachs sont-ils des utilisateurs ? | **Point ouvert** | À valider (S0, S8) |
| PO-13 : Qu'est-ce qu'un abonnement « valable » (date de fin, nombre de séances, plages horaires de la formule) ? *(ajouté après l'analyse IA)* | **Point ouvert** | À valider (S5) |
| PO-14 : Que doit-il se passer à l'entrée si le système est indisponible (panne de réseau ou de courant) ? *(ajouté après l'analyse IA)* | **Point ouvert** | À valider (S3) |

> Les hypothèses H-01 à H-04 ne sont **pas** des exigences : chacune est accompagnée d'un point ouvert à confirmer avec le client.

### Q6 — Élément hors périmètre

**Proposition :** la **gestion des cours collectifs, des plannings et de la réservation de séances avec les coachs**.

**Justification :** la demande ne parle que d'abonnements (S2, S4), de contrôle d'accès (S3, S5–S7) et de fréquentation (S4). Les coachs n'apparaissent qu'à travers leur demande sur l'heure de fin des entrées (S8). Rien dans le texte ne justifie d'inclure leur planning ou la réservation de cours : il est donc écarté du périmètre initial (formulation rigoureuse : « aucune information de la demande ne justifie son inclusion »).

**Éléments classés en point ouvert plutôt qu'en hors périmètre :** le **paiement en ligne** (PO-06), car « renouveler » (S2) peut impliquer un paiement, et l'**inscription de nouveaux adhérents** (PO-11), car la demande ne dit ni oui ni non.

---

## 3. Exigences

### Q7 — Tableau des exigences

| ID | Exigence | Type (F / NF) | Source |
|---|---|---|---|
| REQ-F-01 | Le système doit permettre à un adhérent de consulter son abonnement. | F | S2 |
| REQ-F-02 | Le système doit permettre à un adhérent de renouveler son abonnement. | F | S2 |
| REQ-F-03 | Le système doit refuser l'accès à un adhérent dont l'abonnement n'est pas valable. | F | S3, S5 |
| REQ-F-04 | Le système doit permettre au gérant de suivre la fréquentation de la salle. | F | S4 |
| REQ-F-05 | Le système doit permettre au gérant de gérer les formules d'abonnement. | F | S4 — *exigence initiale, trop ambiguë pour être finale (PO-02)* |
| REQ-NF-01 | Le système doit être moderne et agréable à utiliser. | NF | S10 — *non vérifiable en l'état (PO-10)* |

**Vérification :** chaque exigence commence par « Le système doit… », n'exprime qu'une seule idée et n'introduit aucune fonctionnalité non demandée.

**Besoins exprimés par le client, volontairement non formalisés en exigences tant que les questions ne sont pas levées :**

| Besoin exprimé | Raison | Point ouvert |
|---|---|---|
| Ne pas faire perdre les jours payés aux adhérents en voyage (S2) | Mécanisme inconnu : une exigence vérifiable serait inventée | PO-01 |
| Ne pas bloquer un bon client dont l'abonnement vient de finir (S6) | « Bon client » et « vient de finir » non définis | PO-03 |
| Sanctionner le prêt de carte (S7) | Détection et sanction non définies | PO-04 |
| Arrêter les entrées avant la fermeture (S8, S9) | Conflit entre deux parties prenantes, heure inconnue | PO-05 |

**Traçabilité minimale (besoin → objectif → exigence → source) :**

| Besoin métier | Objectif | Exigence | Source |
|---|---|---|---|
| Empêcher les entrées indues | OBJ-01 | REQ-F-03 | S5 : « Un adhérent ne doit pas pouvoir entrer si son abonnement n'est pas valable. » |
| Faciliter le suivi et le renouvellement par l'adhérent | OBJ-02 | REQ-F-01, REQ-F-02 | S2 |
| Connaître la fréquentation | OBJ-03 | REQ-F-04 | S4 |

### Q8 — Critique de REQ-F-06 et REQ-NF-02 (proposées par une autre équipe)

| Exigence | Problème | Version corrigée / point ouvert |
|---|---|---|
| **REQ-F-06** — Le système doit permettre à l'administration de gérer les salles. | Le verbe « gérer » est ambigu : ajouter, modifier, supprimer, rendre indisponible, gérer la capacité ou les équipements ? Si on choisit une interprétation, on **invente** des fonctionnalités. | Ne pas inventer les opérations. Point ouvert à poser : « Quelles opérations doivent être incluses dans la gestion des salles ? » |
| **REQ-NF-02** — L'application doit être accessible depuis un ordinateur et un smartphone. | La demande dit « un ordinateur **ou** un téléphone » : « et » change le sens (obligation d'être accessible sur les deux), et « smartphone » remplace « téléphone » sans validation. | « Le système doit être accessible depuis un ordinateur ou un téléphone. » À confirmer : doit-il fonctionner sur les deux ou sur l'un des deux au choix ? |

**Transposition à notre sujet :** le même défaut existe pour REQ-F-05 (« gérer les formules d'abonnement », S4) — d'où PO-02. De plus, **notre demande ne mentionne aucun support** (ni ordinateur, ni téléphone) : toute exigence de type « accessible depuis smartphone » serait inventée, elle est donc traitée comme point ouvert PO-08.

### Q9 — Pourquoi « simple à utiliser » (transposé : « moderne et agréable ») n'est pas vérifiable

Notre demande ne contient pas « simple à utiliser » mais **« moderne et agréable » (S10)**, qui pose exactement le même problème : ces termes sont **subjectifs, non quantifiés et sans indicateur de mesure**. Deux personnes différentes peuvent juger différemment la même interface, et aucun test ne permet de dire que l'exigence est satisfaite.

**Questions à poser au client (sans inventer de valeur cible) :**

1. Que signifie « moderne » pour vous : un exemple d'application ou d'interface qui vous plaît ?
2. Qu'est-ce qui rendrait l'application « agréable » pour un adhérent ? Pour un agent d'accueil ?
3. Quel temps maximum jugeriez-vous acceptable pour renouveler un abonnement ? Pour contrôler un adhérent à l'accueil ?
4. L'application doit-elle pouvoir être utilisée sans formation, par un adhérent comme par un agent d'accueil ?
5. Existe-t-il des critères d'ergonomie ou d'accessibilité imposés (lisibilité, langues, personnes en situation de handicap) ?

---

## 4. Analyse IA

**Assistant IA utilisé :** Claude (Anthropic), consulté **après** notre propre analyse (parties 1 à 3).

**Prompt utilisé :**
> Analyse cette demande client pour une salle de sport de quartier (gestion des abonnements et contrôle d'accès). Identifie les ambiguïtés, les informations manquantes et les questions qui devraient être posées au client. N'invente pas de nouvelles exigences.

### Sortie de l'IA (résumée en 12 propositions numérotées)

1. **Contrôle d'accès :** « valable » n'est pas défini. Un abonnement est-il valable selon une date, un nombre de séances, des horaires de la formule ?
2. **Période de grâce :** « bon client » et « vient de finir » ne sont pas définis. Combien de temps de tolérance, et qui décide ?
3. **Voyage :** le mécanisme pour ne pas perdre les jours payés n'est pas précisé (suspension ? prolongation ? durée maximale ? justificatif ?).
4. **Gestion des formules :** « gérer » est ambigu (créer, modifier, retirer, changer les tarifs ?).
5. **Prêt de carte :** la détection et la sanction ne sont pas définies. Le système pourrait utiliser la **reconnaissance faciale** ou un **QR code dynamique** à usage unique pour empêcher le prêt de carte.
6. **Fréquentation :** quels indicateurs ? Faut-il enregistrer uniquement les entrées ou aussi les sorties (présence simultanée dans la salle) ?
7. **Heure limite d'entrée :** coachs et accueil sont en conflit ; l'heure et la personne qui arbitre ne sont pas précisées.
8. **Notifications :** le système devrait envoyer un SMS ou un e-mail **7 jours avant** l'expiration de l'abonnement pour encourager le renouvellement.
9. **Paiement :** faut-il intégrer un **paiement en ligne par carte bancaire** pour le renouvellement ?
10. **Panne / mode dégradé :** que se passe-t-il à l'entrée si le système est indisponible (panne de réseau, de courant) ?
11. **Application native :** développer une application **iOS et Android** pour les adhérents.
12. **« Moderne et agréable » :** critère non mesurable ; il faut définir un indicateur et une valeur cible avec le client.

### Q10 — Classement des propositions de l'IA

| Proposition IA | Décision | Justification (preuve dans la demande ?) |
|---|---|---|
| 1. Définir « abonnement valable » | **Acceptée** | S5 utilise « valable » sans définition : ambiguïté réelle issue du texte (PO-13). |
| 2. Période de grâce / « bon client » | **Acceptée** | S6 parle d'un « bon client » dont l'abonnement « vient de finir » : ambiguïté présente dans le texte (PO-03). |
| 3. Mécanisme voyage | **Acceptée** | S2 mentionne « ceux qui partent en voyage… jours payés », sans mécanisme (PO-01). |
| 4. « Gérer les formules » à préciser | **Acceptée** | S4 : ambiguïté du verbe « gérer » (PO-02). |
| 5. Reconnaissance faciale / QR code dynamique | **Rejetée** (comme exigence) | S7 demande de **sanctionner** le prêt de carte, pas de l'empêcher par une technologie. Solution technique et données biométriques non demandées. Peut devenir une question sur la détection (PO-04). |
| 6. Indicateurs de fréquentation (entrées / sorties) | **À valider** | S4 demande « suivre la fréquentation » sans préciser. Plausible, non confirmé → question ajoutée (PO-07). |
| 7. Conflit heure limite d'entrée | **Acceptée** | S8 et S9 sont explicitement contradictoires : arbitrage du client nécessaire (PO-05). |
| 8. Notifications 7 jours avant expiration | **Rejetée** (comme exigence) | Fonction et délai inventés : rien dans la demande. Peut au mieux devenir une question. |
| 9. Paiement en ligne | **À valider** | « Renouveler » (S2) peut impliquer un paiement, mais rien n'indique le mode. Formulé en point ouvert (PO-06). |
| 10. Panne / mode dégradé | **À valider** | Pertinent pour S3 mais absent de la demande ; formulé en point ouvert (PO-14). |
| 11. Application iOS et Android native | **Rejetée** | Choix technique non demandé ; la demande ne mentionne aucun support (PO-08). |
| 12. « Moderne et agréable » non mesurable | **Acceptée** | S10 : problème réel de vérifiabilité (PO-10). |

### Q11 — Proposition plausible mais inventée

**Proposition choisie : n° 5 — reconnaissance faciale / QR code dynamique pour empêcher le prêt de carte.**

**Pourquoi elle est convaincante :** elle semble répondre directement à un vrai problème cité par le client (S7, le prêt de carte). Elle est courante dans les salles de sport modernes, techniquement crédible, et donne l'impression de résoudre le problème « une fois pour toutes ».

**Pourquoi elle est dangereuse si on l'accepte sans vérification :**
- Le client demande de **sanctionner**, pas d'imposer une technologie de contrôle : on déplace le besoin vers une solution non demandée.
- La reconnaissance faciale implique des **données biométriques** : contraintes légales, consentement, sécurité, coût élevé.
- Elle augmente fortement le périmètre, le matériel nécessaire et le temps de test, pour une salle de quartier de ~400 adhérents.
- Une fois dans les exigences, elle semble « validée » et peut être réalisée à la place de ce que le client attend vraiment.

**Même logique pour la proposition n° 8** (notifications 7 jours avant expiration) : fréquente et utile en apparence, mais fonction et délai inventés.

### Q12 — Ambiguïté relevée par l'IA que notre équipe n'avait pas identifiée

Oui, **deux** :

1. **Enregistrement des sorties** (proposition 6) : nous avions pensé « suivre la fréquentation » uniquement comme un comptage des entrées. L'IA pose la question de savoir s'il faut aussi connaître la **présence simultanée** dans la salle (donc enregistrer les sorties). Cela peut même éclairer le conflit sur l'heure de fermeture (S8) : les coachs ont besoin que la salle se vide pour ranger. Nous n'avions pas vu ce lien car nous traitions S4 et S8 séparément. → ajouté dans PO-07.
2. **Mode dégradé** (proposition 10) : nous n'avions pas envisagé le cas où le système est indisponible à l'entrée (panne). Ce cas n'est pas dans la demande ; nous le transformons en question pour le client (PO-14).

**Chaîne suivie :** IA → suggestion → validation humaine → décision.
