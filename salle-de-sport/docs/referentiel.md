# Référentiel et périmètre — Sujet 5 « Salle de sport : abonnements et accès »

*Partie 2 du TP1 (Q5, Q6).*

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

## Périmètre

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
