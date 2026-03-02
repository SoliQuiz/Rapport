# Cahier des Charges - SoliQuiz

## 1. Présentation du projet

**Nom du projet :** SoliQuiz  
**Type de projet :** Application web d'auto-évaluation et de création de QCM (Questionnaires à Choix Multiples).  
**Bénéficiaire :** Bootcamp / Centre de formation (Formateurs, Étudiants et Administration).  

SoliQuiz est une plateforme pédagogique centralisée permettant la création, le passage et l'analyse de QCM. Son but est d'évaluer de manière granulaire l'acquisition des compétences sur des micro-objectifs d'apprentissage.

---

## 2. Contexte et Problématique

Actuellement, les formateurs du bootcamp s'appuient sur des solutions tierces génériques (Google Forms, fichiers Excel) pour évaluer quotidiennement l'acquisition des connaissances. 

Cette approche génère un état d'**aveuglement pédagogique** caractérisé par plusieurs points critiques :
- **Invisibilité des lacunes** : L'impossibilité technique de lier chaque question à un micro-objectif précis empêche les formateurs d'identifier les notions non comprises en temps réel.
- **Rupture de la continuité administrative** : L'absence de synchronisation avec SoliLMS impose un report manuel des notes, une tâche chronophage et source d'erreurs.
- **Feedback insuffisant** : Les étudiants reçoivent des scores globaux "secs" sans analyse de leurs erreurs, ce qui freine leur progression.
- **Expérience utilisateur fragmentée** : La multiplication d'outils non officiels et l'absence d'interface mobile-first nuisent à l'engagement des apprenants.
- **Pilotage aveugle** : La direction pédagogique ne dispose d'aucune vue globale standardisée pour piloter le taux de réussite des cohortes.

---

## 3. Objectifs du projet

*   **Remplacer Google Forms** par un outil interne adapté 100% au besoin de la formation.
*   **Automatiser les flux d'évaluation** : De la création de QCM au calcul du score final.
*   **Granulométrie du suivi** : Lier chaque QCM et chaque question à un objectif / micro-objectif précis.
*   **Améliorer l'expérience utilisateur** (UX/UI) : Rendre le système agréable, pertinent pour les formateurs, et "stress-free" (auto-sauvegarde, mobile-first, timer) pour les étudiants.
*   **Centraliser et exporter les données** : Produire une API pour la synchronisation des notes directement dans SoliLMS, et offrir des tableaux de bord.

---

## 4. Les Acteurs (Profils Utilisateurs)

Trois types d'utilisateurs distincts interagiront avec l'application :

1.  **L'Étudiant (Apprenti) :**
    *   *But principal :* Passer les QCM quotidiennement, consulter ses notes et suivre sa propre progression.
    *   *Besoins clés :* Une interface claire (mobile ou PC), une sauvegarde continue pour éviter de perdre le travail, des explications (feedback) après validation des réponses.
2.  **Le Formateur :**
    *   *But principal :* Evaluer l'état d'acquisition des connaissances des étudiants pour une session donnée.
    *   *Besoins clés :* Création facile des QCM, associer les QCM à des sessions et des objectifs précis, tableau de bord des résultats de sa classe, calcul automatique des scores.
3.  **L'Administrateur (Direction Pédagogique) :**
    *   *But principal :* Superviser le centre et gérer le système technique de base.
    *   *Besoins clés :* Affecter les rôles et permissions, avoir une vue globale (Dashboard global), préparer la bascule des données vers le SoliLMS centralisé.

---

## 5. Exigences Fonctionnelles (Découpage Agile)

Le développement sera réalisé de manière itérative, organisé en 2 Sprints majeurs.

### 5.1. Sprint 1 : MVP (Minimum Viable Product - Le cœur)
**Focus :** Permettre le cycle vital "Créer -> Passer -> Noter" un QCM.
*   **Authentification basique** et gestion simple des rôles (Admin/Formateur/Étudiant).
*   **CRUD des QCM** par les formateurs (Titre, Description).
*   **Gestion des questions/choix** (Création des questions, options de réponse multiples/uniques, définition des bonnes réponses).
*   **Passation du test** par les étudiants.
*   **Calcul automatique global** du score dès la soumission.

### 5.2. Sprint 2 : Fonctionnalités Avancées (Pédagogie & Analyse)
**Focus :** Granularité pédagogique, analytique et expérience utilisateur avancée.
*   **Liaison Sessions / Objectifs** : Les QCM sont rattachés à des objectifs pédagogiques précis.
*   **Statistiques et KPIs granulaires** : Calcul et affichage du score ventilé par objectif (pour les étudiants et le formateur).
*   **Feedback détaillé** : Affichage des bonnes réponses et d'une explication justifiée ("Pourquoi cette réponse ?") à l'étudiant.
*   **Améliorations UX pour le test** : Mise en place d'un *Compte à rebours (Timer)* et d'un système *d'auto-sauvegarde (Brouillon en temps réel)* des réponses en cours.
*   **Tableau de bord Global** : Interface de statistiques globales pour l'administrateur.
*   **API & Interopérabilité** : Point de terminaison (endpoint / synchronisation) pour faire remonter officiellement les résultats vers **SoliLMS**.

---

## 6. Exigences Non-Fonctionnelles

*   **Responsive Design / Mobile-First :** Extrême importance soulevée par les étudiants (révisions dans les transports). L'interface de passation des tests doit être irréprochable sur smartphone.
*   **Performance et Résilience :** Tolérance à la perte temporaire du réseau côté étudiant (via l'auto-sauvegarde en localStorage par exemple ou sauvegardes API fréquentes).
*   **Ergonomie UI :** Différenciation extrêmement stricte et intuitive visuellement entre une question à choix unique (Boutons Radio) et à choix multiples (Cases à cocher).
*   **Sécurité :** Les QCM ne doivent être accessibles qu'aux étudiants autorisés (via authentification).
*   **Hébergement & Déploiement :** À définir (Cloud interne, VPS, etc.).

---

## 7. Critères d'Acceptation (Définition de fini - DoD)

Pour qu'un Sprint soit considéré comme terminé, les fonctionnalités doivent respecter ces critères :
1.  Le code est revu, testé et intégré dans le dépôt Git principal.
2.  L'étudiant peut passer un QCM complexe de bout en bout sans blocage sur son appareil mobile.
3.  Le temps des formateurs pour créer, faire passer un QCM et obtenir un résultat est mesuré et divisé par deux par rapport à l'ancien processus Google Forms.
4.  Les notes générées sont exactes à 100%.

```{=openxml}
<w:p><w:r><w:br w:type="page"/></w:r></w:p>
```