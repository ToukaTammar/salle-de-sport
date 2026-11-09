# TP1 — Cadrage du projet

**Équipe :** Touka Tammar, Syrine Guermazi, Dhouha Ben Rhouma, Roua Charfeddine  
**Sujet 5 — Salle de sport : abonnements et accès**

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
