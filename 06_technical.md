# Branche Technique

## Choix Technologiques
Pour **SoliQuiz**, nous avons sélectionné une pile technologique moderne garantissant performance et sécurité :

### Backend
- **PHP 8+ & Laravel 12** : Framework MVC robuste pour une logique métier structurée.
- **Eloquent ORM** : Pour une manipulation simplifiée des données.
- **Spatie Laravel Permission** : Gestion des rôles Admin et Apprenant.

### Frontend
- **Blade Templates** : Moteur de rendu natif de Laravel.
- **Tailwind CSS & Preline** : Pour une interface moderne et responsive.
- **Vite** : Outil de build rapide.
- **Alpine.JS** : Pour les interactions dynamiques lors des quiz.

### Base de données
- **MySQL** : Stockage fiable des questions, réponses et utilisateurs.

### Outils Externes
- **Tiptap** : Pour permettre aux administrateurs de rédiger des questions riches.

```{=openxml}
<w:p><w:r><w:br w:type="page"/></w:r></w:p>
```

## Architecture Système
### Architecture MVC
Laravel organise le code en Modèles (données), Vues (interfaces) et Contrôleurs (logique), assurant une séparation nette des responsabilités.

### Architecture 3-Tier
1. **Couche Présentation** : Vues Blade et UI Tailwind.
2. **Couche Métier** : Logique de validation et de scoring dans les contrôleurs.
3. **Couche Données** : Modèles Eloquent et MySQL.

### Architecture Globale
Le système est conçu pour être modulaire, permettant à l'application web et à une future application mobile de consommer les mêmes services via une API REST.

```{=openxml}
<w:p><w:r><w:br w:type="page"/></w:r></w:p>
```

## Prototype (Fonctionnalités et Classes)
### 1. Section Administrateur (Formateur)
L’interface d’administration est conçue pour offrir aux formateurs une autonomie totale dans la gestion des évaluations :
- **Rédaction enrichie** : Création de questions complexes utilisant l'éditeur Tiptap (formatage, listes, extraits de code).
- **Configuration des réponses** : Ajout flexible de choix multiples et définition précise des bonnes réponses.
- **Vérification et Aperçu** : Possibilité de tester le quiz en mode "aperçu" pour valider le rendu visuel et la logique de correction avant diffusion.
- **Suivi en temps réel** : Analyse des taux de réussite par question et par objectif pédagogique.

### 2. Section Publique (Apprenant)
Consultation des catégories, passage de quiz chronométrés et affichage immédiat des résultats.

### 3. API
Endpoints sécurisés pour la récupération des quiz et la soumission des scores depuis des clients externes.

### Les classes principales
- **User** : {id, name, email, role}
- **Quiz** : {id, title, description, category_id}
- **Question** : {id, quiz_id, text, points}
- **Answer** : {id, question_id, text, is_correct}

```{=openxml}
<w:p><w:r><w:br w:type="page"/></w:r></w:p>
```