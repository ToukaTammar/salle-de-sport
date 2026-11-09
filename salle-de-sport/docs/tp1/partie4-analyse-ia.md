# TP1 — Partie 4 : analyse critique assistée par IA (Q10 à Q12)

**Sujet 5 — Salle de sport : abonnements et accès**

> Les références **S0 à S10** renvoient aux phrases de la demande client et **PO-xx / H-xx** aux points ouverts et hypothèses de la partie 2 (`tp1-partie2-savoir-ne-pas-savoir.md`).

**Assistant IA utilisé :** Claude (Anthropic), consulté **après** notre propre analyse (parties 1 à 3).

**Prompt utilisé :**
> Analyse cette demande client pour une salle de sport de quartier (gestion des abonnements et contrôle d'accès). Identifie les ambiguïtés, les informations manquantes et les questions qui devraient être posées au client. N'invente pas de nouvelles exigences.

## Sortie de l'IA (résumée en 12 propositions numérotées)

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

## Q10 — Classement des propositions de l'IA

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

## Q11 — Proposition plausible mais inventée

**Proposition choisie : n° 5 — reconnaissance faciale / QR code dynamique pour empêcher le prêt de carte.**

**Pourquoi elle est convaincante :** elle semble répondre directement à un vrai problème cité par le client (S7, le prêt de carte). Elle est courante dans les salles de sport modernes, techniquement crédible, et donne l'impression de résoudre le problème « une fois pour toutes ».

**Pourquoi elle est dangereuse si on l'accepte sans vérification :**
- Le client demande de **sanctionner**, pas d'imposer une technologie de contrôle : on déplace le besoin vers une solution non demandée.
- La reconnaissance faciale implique des **données biométriques** : contraintes légales, consentement, sécurité, coût élevé.
- Elle augmente fortement le périmètre, le matériel nécessaire et le temps de test, pour une salle de quartier de ~400 adhérents.
- Une fois dans les exigences, elle semble « validée » et peut être réalisée à la place de ce que le client attend vraiment.

**Même logique pour la proposition n° 8** (notifications 7 jours avant expiration) : fréquente et utile en apparence, mais fonction et délai inventés.

## Q12 — Ambiguïté relevée par l'IA que notre équipe n'avait pas identifiée

Oui, **deux** :

1. **Enregistrement des sorties** (proposition 6) : nous avions pensé « suivre la fréquentation » uniquement comme un comptage des entrées. L'IA pose la question de savoir s'il faut aussi connaître la **présence simultanée** dans la salle (donc enregistrer les sorties). Cela peut même éclairer le conflit sur l'heure de fermeture (S8) : les coachs ont besoin que la salle se vide pour ranger. Nous n'avions pas vu ce lien car nous traitions S4 et S8 séparément. → ajouté dans PO-07.
2. **Mode dégradé** (proposition 10) : nous n'avions pas envisagé le cas où le système est indisponible à l'entrée (panne). Ce cas n'est pas dans la demande ; nous le transformons en question pour le client (PO-14).

**Chaîne suivie :** IA → suggestion → validation humaine → décision.
