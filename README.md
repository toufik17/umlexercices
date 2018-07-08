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

___Partie 1 : Description.___

- Titre : Retirer de l’argent.
- Résumé : Ce cas d’utilisation permet aux possesseurs de carte bancaire de retire de l’argent.
- Acteur principale : Un porteur de carte bancaire.
- Acteurs secondaires : Le Système d’Information de la banque et le Système d’Autorisation Globale Carte Bancaire.
- Date : 08/07/2018
- Responsable : E. Dupon
- Version : 1.0

___Partie 2 : Description des scénarios.___

- Pré-conditions :
- Le DAB contient des billets.
- Les connexions avec le Système d’Autorisation et le Système d’information de la banque sontopérationnelles.

- Scénario nominale :
<ol>
   <li>Le Porteur de carte introduit sa carte dans le DAB.</li>
   <li>Le DAB vérifie que la carte introduite est bien une carte bancaire.</li>
   <li>Le DAB demande le code de la carte au Porteur de carte.</li>
   <li>Le Porteur de carte saisit son code.</li>
   <li>Le DAB compare ce code avec celui qui est codé sur la carte.</li>
   <li>Le DAB demande une autorisation au Système Globale d’autorisation.</li>
   <li>Le Système d’Autorisation globale donne son accord et indique le crédit hebdomadaire.</li>
   <li>Le DAB demande le montant désiré au Porteur de carte.</li>
   <li>Le Porteur de carte saisit le montant.</li>
   <li>Le DAB vérifie si le montant demandé est inférieur ou égale au crédit hebdomadaire.</li>
   <li>Le DAB rend la carte et demande au Porteur de carte de la retirer.</li>
   <li>Le Porteur de carte reprend sa carte.</li>
   <li>Le DAB demande au Porteur de carte s’il désire un ticket.</li>
   <li>Le Porteur de carte accepte le ticket.</li>
   <li>Le DAB délivre le ticket et les billets.</li>
   <li>Le Porteur de carte prends les billets et le ticket.</li>
</ol>
- Scénarios alternatifs :
<ul>
   <li>Scénario alternatif SA1:</li>
      <ul>
      <li>Le code est erroné pour la première ou la deuxième fois.</li>
      <li>SA1 commence au point 5 du scénario nominale.</li>
      <li>Le DAB indique que le code est erroné.</li>
      <li>Le DAB enregistre l’échec.</li>
      <li>Le scénario reprend au point 3 du scénario nominal.</li>
     </ul>
 </ul>
 
 <ul>
   <li>Scénario alternatif SA2: </li>
    <ul>
    <li>Le montant demandé est trop élevé.</li>
    <li>SA2 commence au point 10 du scénario nominale.</li>
    <li>Le DAB affiche le montant max et demande au Porteur de carte de ressaisir un montant.</li>
    <li>Le scénario reprend au point 9 du scénario nominal.</li>
     </ul>
 </ul>
 
<ul>
   <li>Scénario alternatif SA3: </li>
   <ul>
    <li>Le ticket est refusé.</li></li>
    <li>SA1 commence au point 13 du scé</li>nario nominale.</li>
    <li>14. L’utilisateur refuse le ticket.</li>
    <li>15. Le DAB délivre les billets.</li>
    <li>16. L’utilisateur prend les billets.</li>
     </ul>
 </ul>
 
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

___Partie 3 : Exigences non fonctionnelles___

La saisie du code confidentiel ne doit pas faire apparaître le code à l’écran.
Le compte du client ne doit pas être débité tant que le billets n’ont pas été distribués.
