# umlexercices

Le DAB (Distributeur Automatique de Billet)

- Un DAB permet à tout détenteur de carte bancaire de retirer de l’argent.
- Si le détenteur de carte est un client de la banque propriétaire du DAB, il peut en plus consulter les soldes de ses comptes et effectuer des virements entres ces différents comptes.
- Les transactions sont sécurisées c’est-à-dire :
- Le DAB consulte le Système d’Information de la banque (S.I. Banque) pour les opérations que désire effectuer un client de la banque (retraits, consultation soldes et virements).
- Le DAB consulte le Système d’Autorisation Globale Carte Bancaire (Sys. Auto.) pour les retraits des porteurs de cartes non clients de la banque.
- Le DAB nécessite des opérations de maintenance tel que la recharge en billet, la récupération des cartes avalée, etc.

Après discussion avec l’expert métier, il apparaît que l’une des sous fonctions importantes est
l’authentification (systématique et commune au 3 cas d’utilisations Retirer de l’argent,
Consulter ses soldes et Effectuer un virement).
- Le DAB permet à son utilisateur d’imprimer un reçu s’il le désire.
- L’expert métier précise que le DAB sera situé dans une zone internationale et devra donc pouvoir fournir la somme d’argent en Dollars ou en Euros.

__Correction :__

![img](https://github.com/toufik17/umlexercices/blob/master/dab.JPG)

__Exemple de description textuelle : Le cas d‘utilisation ‘Retirer de l’argent’ du DAB.__
Partie 1 : Description.
- Titre : Retirer de l’argent.
- Résumé : Ce cas d’utilisation permet aux possesseurs de carte bancaire de retire de l’argent.
- Acteur principale : Un porteur de carte bancaire.
- Acteurs secondaires : Le Système d’Information de la banque et le Système d’Autorisation
Globale Carte Bancaire.
- Date : 11/01/2013
- Responsable : E. REMY
- Version : 1.0
Partie 2 : Description des scénarios.
- Pré-conditions :
- Le DAB contient des billets.
- Les connexions avec le Système d’Autorisation et le Système d’information de la banque sont
opérationnelles.
- Scénario nominale :
1) Le Porteur de carte introduit sa carte dans le DAB.
2) Le DAB vérifie que la carte introduite est bien une carte bancaire.
3) Le DAB demande le code de la carte au Porteur de carte.
4) Le Porteur de carte saisit son code.
5) Le DAB compare ce code avec celui qui est codé sur la carte.
6) Le DAB demande une autorisation au Système Globale d’autorisation.
7) Le Système d’Autorisation globale donne son accord et indique le crédit hebdomadaire.
8) Le DAB demande le montant désiré au Porteur de carte.
9) Le Porteur de carte saisit le montant.
10) Le DAB vérifie si le montant demandé est inférieur ou égale au crédit hebdomadaire.
11) Le DAB rend la carte et demande au Porteur de carte de la retirer.
12) Le Porteur de carte reprend sa carte.
13) Le DAB demande au Porteur de carte s’il désire un ticket.
14) Le Porteur de carte accepte le ticket.
15) Le DAB délivre le ticket et les billets.
16) Le Porteur de carte prends les billets et le ticket.
6/9
- Scénarios alternatifs :
• Scénario alternatif SA1: Le code est erroné pour la première ou la deuxième fois.
SA1 commence au point 5 du scénario nominale.
Le DAB indique que le code est erroné.
Le DAB enregistre l’échec.
Le scénario reprend au point 3 du scénario nominal.
• Scénario alternatif SA2: Le montant demandé est trop élevé.
SA2 commence au point 10 du scénario nominale.
Le DAB affiche le montant max et demande au Porteur de carte de ressaisir un montant.
Le scénario reprend au point 9 du scénario nominal.
• Scénario alternatif SA3: Le ticket est refusé.
SA1 commence au point 13 du scénario nominale.
14) L’utilisateur refuse le ticket.
15) Le DAB délivre les billets.
16) L’utilisateur prend les billets.
• Scénario alternatif SA4: Le porteur de carte est client de la banque.
SA1 commence au point 7 du scénario nominale.
Le DAB demande une autorisation auprès du Système d’Information de la banque.
Le scénario reprend au point 9 du scénario nominal.
- Scénarios d’exception:
• Scénario d’exception SE1: Carte non valide.
SE1 commence au point 2 du scénario nominal.
Le DAB Indique que la carte n’est pas valide restitue la carte et met fin au cas.
• Scénario d’exception SE2: Le code est erroné pour la troisième fois.
SE2 commence au point 5 du scénario nominal.
Le DAB Indique que le code est erroné pour la troisième fois, confisque la carte et met fin au cas.
• Scénario d’exception SE3: Retrait non autorisé.
SE3 commence au point 6 du scénario nominal.
Le DAB Indique que tout retrait est impossible, restitue la carte et met fin au cas.
• Scénario d’exception SE4: Carte non reprise.
SE4 commence au point 11 du scénario nominal.
Au bout de 30s, le DAB confisque la carte et met fin au cas.
• Scénario d’exception SE5: Billets non pris.
SE5 commence au point 15 du scénario nominal.
Au bout de 30s, le DAB reprend les billets et met fin au cas.
• Scénario d’exception SE6: Annulation de la transaction.
SE6 peut démarrer entre les points 4 et 9 du scénario nominal.
Le DAB éjecte la carte et met fin au cas.
- Post-conditions:
Les détails de la transaction doivent être enregistrés (montant, numéro carte, date…) aussi bien
en cas de succès que d’échec.
Partie 3 : Exigences non fonctionnelles
La saisie du code confidentiel ne doit pas faire apparaître le code à l’écran.
Le compte du client ne doit pas être débité tant que le billets n’ont pas été distribués.
