# TP-outils-formel
1. Présentation des spécifications initiales
Le système  comporte les fonctionnalités suivantes :
Vérification du numéro de carte utilisateur.
Vérification du mot de passe correspondant.
Gestion des tentatives incorrectes avec un déclenchement d'alarme après trois échecs consécutifs.
Indication claire des états du système tout au long du processus.

2. Description des modèles d'automates et des circuits logiques réalisés
Le système est modélisé à l'aide d'états finis représentés dans la classe Etats, comportant les états suivants :
CodeUtilisateur : État initial où l'utilisateur entre son numéro de carte.
MotdDP : État où l'utilisateur entre le mot de passe.
VerifMDP : Vérification de la validité du mot de passe.
AccesAutorise : Accès accordé, suivi de l'ouverture des portes.
AccesRefuse : Accès refusé en cas d'erreur.
AlarmeDeclenchee : État final après trois tentatives incorrectes.

La gestion des états est déclenchée par des conditions logiques vérifiant la validité des informations saisies par l'utilisateur. La transition d'un état à l'autre est implémentée dans les méthodes VerifCodeU et verifMDP de la classe Etats.

3. Résultats des vérifications formelles et des optimisations
J'ai  testé le système  dans différents scénarios pour vérifier sa robustesse :

Cas nominal : L'utilisateur entre le bon numéro de carte et le bon mot de passe dès la première tentative. Résultat : Accès autorisé, ouverture des portes.

Cas d'erreur : L'utilisateur entre un numéro de carte ou un mot de passe incorrect. Résultat : Accès lui est refusé avec message indiquant le nombre de tentatives restantes.

Cas d'échec : Après trois tentatives incorrectes, le système déclenche un compte à rebours et active une alarme. Résultat : Alarme correctement déclenchée.

Optimisations  :
Utilisation d'une boucle pour gérer les tentatives et simplifier la logique de vérification.
Ajout de délais avec Thread.sleep() pour simuler un compte à rebours réaliste avant le déclenchement de l'alarme.

4. Discussion des défis rencontrés et des solutions apportées
 
Le seul défi que j'ai rencontré était la Gestion du temps pour le compte à rebours de l'alarme.
 Pour régler cela ,j'ai utilisé Thread.sleep() pour simuler un intervalle temporel.



5. Conclusion sur l'efficacité et la fiabilité du système conçu

Le système conçu est efficace pour gérer les scénarios classiques de contrôle d'accès que ce soit dans un immeuble ou tout autre batiment :
Les transitions d'états sont fluides et adaptées à chaque situation.
La gestion des tentatives et du déclenchement de l'alarme est fiable.
