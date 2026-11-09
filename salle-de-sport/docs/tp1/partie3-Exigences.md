## 3. Exigences

### Q7 — Exigences possibles et traçabilité

| ID | Exigence | Type | Source | Appréciation |
|---|---|---|---|---|
| REQ-F-01 | Le système doit permettre à un adhérent de consulter son abonnement. | F | S2 : « Les adhérents doivent pouvoir consulter leur abonnement… » | Acceptable. |
| REQ-F-02 | Le système doit permettre à un adhérent de renouveler son abonnement. | F | S2 : « …et le renouveler » | Acceptable. Le paiement n'est pas précisé (PO-06). |
| REQ-F-03 | Le système doit refuser l'accès à un adhérent dont l'abonnement n'est pas valable. | F | S3, S5 : « Un adhérent ne doit pas pouvoir entrer si son abonnement n'est pas valable. » | Acceptable, mais « valable » doit être défini (PO-13). |
| REQ-F-04 | Le système doit permettre au gérant de suivre la fréquentation de la salle. | F | S4 : « …suivre la fréquentation de la salle. » | Acceptable comme exigence initiale. Les indicateurs sont à préciser (PO-07). |
| REQ-F-05 | Le système doit permettre au gérant de gérer les formules d'abonnement. | F | S4 : « Le gérant veut gérer les formules d'abonnement… » | Acceptable comme exigence initiale, mais trop ambiguë pour être finale (PO-02). |
| REQ-F-06 | Le système doit permettre à un adhérent qui part en voyage de ne pas perdre les jours payés de son abonnement. | F | S2 : « …ceux qui partent en voyage ne veulent pas perdre les jours payés. » | Acceptable comme exigence initiale, mais le mécanisme est inconnu (PO-01). |
| REQ-F-07 | Le système doit autoriser l'accès à un bon client dont l'abonnement vient de finir. | F | S6 : « Il ne faut pas non plus bloquer à la porte un bon client dont l'abonnement vient de finir. » | À raffiner : « bon client » et « vient de finir » ne sont pas définis (PO-03). À rendre cohérente avec REQ-F-03 une fois « valable » défini (PO-13). |
| REQ-F-08 | Le système doit permettre de sanctionner un adhérent qui prête sa carte à un tiers. | F | S7 : « Certains adhérents prêtent leur carte à des amis : il faut les sanctionner. » | Trop ambiguë : détection et sanction non définies (PO-04). |
| REQ-NF-01 | Le système doit être moderne. | NF | S10 : « L'application doit être moderne et agréable. » | Besoin initial à raffiner, non vérifiable en l'état (PO-10). |
| REQ-NF-02 | Le système doit être agréable à utiliser. | NF | S10 | Même remarque (PO-10). |

**Non formalisé en exigence : conflit entre deux parties prenantes**

| Besoin exprimé | Raison | Point ouvert |
|---|---|---|
| Arrêter les entrées bien avant la fermeture (S8) et laisser entrer jusqu'à la dernière minute (S9) | Deux demandes contradictoires : l'une des deux exigences violerait le critère de cohérence, et l'heure limite est inconnue. | PO-05 |

**Traçabilité minimale (besoin → objectif → exigence → source)**

| Besoin métier | Objectif | Exigence | Source |
|---|---|---|---|
| Empêcher les entrées indues | OBJ-01 | REQ-F-03 | S5 : « Un adhérent ne doit pas pouvoir entrer si son abonnement n'est pas valable. » |
| Empêcher l'usage de la carte d'un autre | OBJ-01 | REQ-F-08 | S7 : « Certains adhérents prêtent leur carte à des amis : il faut les sanctionner. » |
| Faciliter le suivi et le renouvellement par l'adhérent | OBJ-02 | REQ-F-01, REQ-F-02, REQ-F-06 | S2 : « Les adhérents doivent pouvoir consulter leur abonnement et le renouveler… » |
| Connaître la fréquentation | OBJ-03 | REQ-F-04 | S4 : « …suivre la fréquentation de la salle. » |

### Q8 — Critique de REQ-F-06 et REQ-NF-02 (autre équipe)

| Exigence | Problème | Réponse attendue |
|---|---|---|
| **REQ-F-06 (autre équipe)** — Le système doit permettre à l'administration de gérer les salles. | Le verbe « gérer » est ambigu : ajouter, modifier, supprimer, rendre indisponible, gérer la capacité ou les équipements ? Choisir une interprétation reviendrait à inventer des fonctionnalités. | Ne pas inventer les opérations. Poser la question au client : « Quelles opérations doivent être incluses dans la gestion des salles ? » |
| **REQ-NF-02 (autre équipe)** — L'application doit être accessible depuis un ordinateur et un smartphone. | « Smartphone » remplace « téléphone » sans validation du client. Le « et » à la place de « ou » est aussi à confirmer. | « Le système doit être accessible depuis un ordinateur ou un téléphone. » À confirmer avec le client : les deux supports sont-ils obligatoires, ou l'un des deux au choix ? |

**Transposition à notre sujet :** le même défaut existe pour REQ-F-05 (« gérer les formules », PO-02). Notre demande ne mentionne aucun support : toute exigence d'accessibilité serait inventée, donc elle est traitée en point ouvert (PO-08).

### Q9 — « Moderne et agréable » : pourquoi ce n'est pas vérifiable

Notre demande ne contient pas « simple à utiliser », mais « moderne et agréable » (S10) pose le même problème. Ces termes sont **subjectifs, non quantifiés et sans indicateur de mesure** : deux personnes peuvent juger différemment la même interface, et aucun test ne permet de conclure que l'exigence est satisfaite.

**Questions à poser au client:**

1. Que signifie « moderne » pour vous ? Avez-vous un exemple d'application qui vous plaît ?
2. Qu'est-ce qui rendrait l'application « agréable » pour un adhérent ? Pour un agent d'accueil ?
3. Quel temps maximum est acceptable pour renouveler un abonnement ? Pour contrôler un adhérent à l'accueil ?
4. Combien d'étapes maximum souhaitez-vous pour renouveler un abonnement ?
5. Quel taux de réussite attendez-vous lors d'un test utilisateur ?
6. Le système doit-il être utilisable sans formation, par un adhérent comme par un agent d'accueil ?
7. Existe-t-il des critères d'accessibilité ou d'ergonomie imposés ?

Les questions 3 à 6 sont propres à cette partie. Elles complètent la liste complète des questions client dans `questions-client.md`, qui renvoie à chaque point ouvert (PO).
