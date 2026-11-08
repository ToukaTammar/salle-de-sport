# Exigences et traçabilité — Sujet 5 « Salle de sport : abonnements et accès »

*Partie 3 du TP1 (Q7, Q8, Q9).*

> Les références **S0 à S10** renvoient aux phrases numérotées de la demande client (voir `referentiel.md`).


## Q7 — Tableau des exigences

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

## Q8 — Critique de REQ-F-06 et REQ-NF-02 (proposées par une autre équipe)

| Exigence | Problème | Version corrigée / point ouvert |
|---|---|---|
| **REQ-F-06** — Le système doit permettre à l'administration de gérer les salles. | Le verbe « gérer » est ambigu : ajouter, modifier, supprimer, rendre indisponible, gérer la capacité ou les équipements ? Si on choisit une interprétation, on **invente** des fonctionnalités. | Ne pas inventer les opérations. Point ouvert à poser : « Quelles opérations doivent être incluses dans la gestion des salles ? » |
| **REQ-NF-02** — L'application doit être accessible depuis un ordinateur et un smartphone. | La demande dit « un ordinateur **ou** un téléphone » : « et » change le sens (obligation d'être accessible sur les deux), et « smartphone » remplace « téléphone » sans validation. | « Le système doit être accessible depuis un ordinateur ou un téléphone. » À confirmer : doit-il fonctionner sur les deux ou sur l'un des deux au choix ? |

**Transposition à notre sujet :** le même défaut existe pour REQ-F-05 (« gérer les formules d'abonnement », S4) — d'où PO-02. De plus, **notre demande ne mentionne aucun support** (ni ordinateur, ni téléphone) : toute exigence de type « accessible depuis smartphone » serait inventée, elle est donc traitée comme point ouvert PO-08.

## Q9 — Pourquoi « simple à utiliser » (transposé : « moderne et agréable ») n'est pas vérifiable

Notre demande ne contient pas « simple à utiliser » mais **« moderne et agréable » (S10)**, qui pose exactement le même problème : ces termes sont **subjectifs, non quantifiés et sans indicateur de mesure**. Deux personnes différentes peuvent juger différemment la même interface, et aucun test ne permet de dire que l'exigence est satisfaite.

**Questions à poser au client (sans inventer de valeur cible) :**

1. Que signifie « moderne » pour vous : un exemple d'application ou d'interface qui vous plaît ?
2. Qu'est-ce qui rendrait l'application « agréable » pour un adhérent ? Pour un agent d'accueil ?
3. Quel temps maximum jugeriez-vous acceptable pour renouveler un abonnement ? Pour contrôler un adhérent à l'accueil ?
4. L'application doit-elle pouvoir être utilisée sans formation, par un adhérent comme par un agent d'accueil ?
5. Existe-t-il des critères d'ergonomie ou d'accessibilité imposés (lisibilité, langues, personnes en situation de handicap) ?
