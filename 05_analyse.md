# Branche fonctionnelle

## Interviews d'empathie

### Compte rendu — Remarques du formateur Youssef (19/02/2026)
**Objectif** : Recueillir les besoins liés à la gestion des QCM afin d’évaluer les connaissances des apprenants.

#### 1. Organisation des QCM
- Chaque session doit avoir son propre **QCM**.
- Il ne faut pas créer un QCM global pour tout le module.
- Chaque objectif doit également avoir son propre **QCM**.

#### 2. Liaison avec les professeurs
- Le QCM doit être lié au professeur.
- Les professeurs doivent avoir accès aux :
  - **Questions** (ajout des questions)
  - **Choix** (ajout des choix)
  - **Réponses** (affichage des réponses)

#### 3. Correction et calcul des résultats
- Le calcul des résultats doit être effectué automatiquement par le système.
- Le système doit calculer le score par objectif.

---

### Compte rendu — Remarques de la formatrice Fatine (19/02/2026)
**Objectif** : Recueillir les besoins liés à la gestion des QCM.

#### 1. Création et organisation des QCM
- Les formateurs doivent pouvoir créer des **QCM** facilement.
- Chaque QCM doit contenir :
  - **Questions** (ajout, modification et suppression)
  - **Choix multiples** pour chaque question.
  - Définition de la ou des **bonnes réponses**.
  - Choix du **nombre de questions** dans le QCM.
  - Définition du **nombre de réponses** possibles par question.

#### 2. Fonctionnalités attendues
- L’application doit permettre une gestion simple et rapide.
- Elle doit offrir une interface claire et intuitive avec une flexibilité dans le nombre de choix.

#### 3. Correction et calcul des résultats
- Le calcul des résultats doit être automatique.
- Le système doit calculer le score total et l'afficher à l’étudiant.

---

### Compte rendu — Remarques de l'étudiant Mehdi (26/02/2026)
**Objectif** : Identifier les points de frustration et les besoins techniques concrets des étudiants.

#### 1. Frustrations et Problèmes Techniques
- **Accessibilité Mobile** : "On révise souvent dans les transports ou pendant les pauses, l'outil doit être fluide sur smartphone. Actuellement, certains formulaires sont illisibles sur petit écran."
- **Instabilité des sessions** : Peur de perdre ses réponses en cas de micro-coupure internet ou si l'on change d'onglet par inadvertance.
- **Temps Limité** : Besoin d'un compte à rebours visible pour ne pas se faire surprendre par la clôture automatique du test.

#### 2. Clarté et Ergonomie
- **Ambiguïté des questions** : "Parfois on ne sait pas si c'est une seule réponse possible ou plusieurs (Case à cocher vs Bouton radio)."
- **Navigation** : Souhaite pouvoir revenir sur une question précédente avant la validation finale (possibilité de révision).

---

### Compte rendu — Remarques de l'étudiant Soufiane (26/02/2026)
**Objectif** : Analyser les besoins en termes de motivation, de feedback et de suivi de progression.

#### 1. Feedback et Apprentissage
- **Correction Immédiate** : "Recevoir juste une note ne m'aide pas. Je veux voir tout de suite quelles questions j'ai ratées et pourquoi la bonne réponse était la bonne."
- **Analyse par Compétence** : Besoin de voir ses points forts et faibles par objectif pédagogique.

---

## Carte d’empathie
L’analyse de l’utilisateur nous a permis de comprendre que les apprenants de Solicode ont besoin d’un outil simple pour valider leurs connaissances sans stress, tandis que les formateurs ont besoin d'une autonomie totale sur la création des tests.

![Carte d'empathie - Formateur Youssef](images/carte-empathie-formateur-youssef-soliquiz.png)

![Carte d'empathie - Formatrice Fatine](images/carte-empathie-formatrice-fatine-soliquiz.png)

![Carte d'empathie - Étudiant Mehdi](images/carte-empathie-etudiant-mehdi-soliquiz.png)

![Carte d'empathie - Étudiant Soufiane](images/carte-empathie-etudiant-soufiane-soliquiz.png)

## Définition du problème

Le problème majeur identifié est la lourdeur de la **saisie manuelle des notes** dans SoliLMS après chaque évaluation quotidienne. Le fait de devoir saisir les notes manuellement en SoliLMS après l'évaluation constitue le point critique : cela prend un temps considérable aux formateurs, génère des erreurs de saisie et retarde le suivi pédagogique. De plus, le manque d'un outil centralisé et interactif pour l'auto-évaluation quotidienne au sein du bootcamp empêche un suivi précis lié aux micro-objectifs de formation.

### Problèmes secondaires

Actuellement, les QCM sont réalisés via Google Forms, ce qui ne répond plus aux besoins pédagogiques des formateurs. Après la phase d’empathie menée avec les formateurs, plusieurs limites ont été identifiées :

* **Absence de liaison structurée** entre les QCM, les sessions, les modules et les objectifs pédagogiques.
* **Difficulté à attribuer un QCM spécifique** à chaque session et à chaque objectif.
* **Manque de centralisation** : les professeurs ne disposent pas d’un espace unique pour gérer leurs QCM.
* **Absence d’un calcul automatique détaillé** des scores par objectif.
* **Difficulté de suivi clair** des résultats des étudiants, empêchant un feedback pédagogique immédiat.



## Sprints backlog
Le backlog a été organisé pour prioriser :
1. La connexion avec l'API de **SoliLMS** pour récupérer les données des apprenants et formateurs.
2. La gestion des quiz par objectifs pédagogiques.
3. L'automatisation de la remontée des scores vers SoliLMS pour éliminer la saisie manuelle.

## Diagramme de cas d’utilisation
Le diagramme de cas d’utilisation de **SoliQuiz** illustre les fonctionnalités clés :
- **Apprenant** (Synchronisé via SoliLMS) : Passer ses quiz quotidiens et consulter ses scores instantanés.
- **Formateur** (Synchronisé via SoliLMS) : Créer des QCM par objectif et consulter les résultats automatisés.
- **Système** : Assurer la synchronisation bidirectionnelle avec **SoliLMS** pour les utilisateurs et les notes.

```{=openxml}
<w:p><w:r><w:br w:type="page"/></w:r></w:p>
```