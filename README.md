# Les Tests

Bienvenue dans cette ressource pédagogique sur les tests informatiques – un passage incontournable pour tout développeur ou développeuse qui veut écrire du code robuste et fiable. Prêts à améliorer vos compétences ? Let's go ! 🚀

---

## Sommaire
1. [Les différents types de tests automatisés](#les-différents-types-de-tests-automatisés)
   - [Tests Unitaires](#1-tests-unitaires)
   - [Tests d’Intégration](#2-tests-dintégration)
   - [Tests Fonctionnels (ou Système)](#3-tests-fonctionnels-ou-système)
   - [Tests d’Acceptation](#4-tests-dacceptation)
2. [Les tests End-to-End (E2E)](#les-tests-end-to-end-e2e)
3. [Les autres types de tests](#les-autres-types-de-tests)
4. [Le Test Coverage](#le-test-coverage)
5. [La pyramide des tests](#la-pyramide-des-tests)
6. [Les doubles de Test](#les-doubles-de-test)
7. [Arrange, Act, Assert](#arrange-act-assert)
8. [Les méthodes et bonnes pratiques autour des tests](#les-méthodes-et-bonnes-pratiques-autour-des-tests)
   - [TDD (Test-Driven Development)](#1-tdd-test-driven-development)
   - [Test First](#2-test-first)
   - [BDD (Behavior-Driven Development)](#3-bdd-behavior-driven-development)
9. [Présentations](#présentations)
10. [Exercices](#exercices)
11. [Ressources](#ressources)

---

## Les différents types de tests automatisés

### 1. **Tests Unitaires**
Les tests unitaires valident le fonctionnement isolé d'une petite partie de code (souvent une fonction ou une méthode).

- **Objectif** : Vérifier qu'une unité de code (une fonction ou méthode) fonctionne correctement de manière **indépendante**.
- **Caractéristiques** :
  - Faciles à écrire et rapides à exécuter.
  - Fournissent une documentation vivante sur le fonctionnement attendu du code.
  - Nécessitent parfois d'utiliser des **doubles** afin d'isoler le code testé.
- **Exemple** : Tester une fonction qui calcule une somme.

---

### 2. **Tests d’Intégration**
Ils vérifient comment plusieurs modules ou services fonctionnent ensemble.

- **Objectif** : S'assurer que des modules ou services interagissent correctement.
- **Caractéristiques** :
  - Testent des combinaisons spécifiques de composants.
  - Nécessitent parfois des ressources externes (bases de données, API).
- **Exemple** : Tester un appel à une API qui enregistre des utilisateurs en base de données, et les retourne dans une liste.
  
---

### 3. **Tests Fonctionnels (ou Système)**
Les tests fonctionnels vérifient que le système dans son ensemble respecte les exigences métier ou techniques.

- **Objectif** : Valider le comportement global d'une application par rapport à ses spécifications.
- **Caractéristiques** :
  - Utilisent des scénarios simulant des actions utilisateur.
  - Peuvent nécessiter des environnements proches de la production.
- **Exemple** : Vérifier qu'un utilisateur peut passer une commande avec succès sur un site e-commerce.

---

### 4. **Tests d’Acceptation**
Les tests d'acceptation valident que le produit correspond aux besoins et attentes des utilisateurs ou clients.

- **Objectif** : Obtenir le feu vert des utilisateurs avant le déploiement.
- **Caractéristiques** :
  - Réalisés souvent en collaboration avec les clients.
  - Écrits en langage clair et compréhensible (souvent en BDD).
- **Exemple** : Valider un flux complet de réservation de billet.

---

## Les tests End-to-End (E2E)
Ces tests reproduisent le parcours utilisateur complet d'un bout à l'autre.

- **Objectif** : Tester une application dans sa globalité pour vérifier qu'elle fonctionne correctement du point de vue de l'utilisateur.
- **Caractéristiques** :
  - Exécutés sur un environnement similaire à la production.
  - Incluent des tests sur des navigateurs ou dispositifs réels.
- **Exemple** : Vérifier qu'un utilisateur peut s'inscrire, se connecter et accéder à son profil sans erreur.

---

## Les autres types de tests

- **Tests de Performance** :
  - Mesurent la vitesse, la réactivité et la stabilité du système.

- **Tests de Charge** :
  - Évaluent le comportement sous une forte charge utilisateur.
  - Utilité : Prévoir les performances sous pression.

- **Tests de Sécurité** :
  - Identifient les failles de sécurité (injection SQL, XSS, etc.).

- **Tests de Régression (ou Non-régression)** :
  - Vérifient qu'une modification du code n'a pas introduit de nouveaux bugs.

---

## Le Test Coverage

La couverture des tests (ou "test coverage") mesure le pourcentage de code exécuté par les tests.

- **Objectif** : Identifier les parties du code qui ne sont pas couvertes par des tests.
- **Utilité** :
  - Aide à repérer les zones vulnérables ou non testées du code.
  - Sert de métrique pour évaluer la robustesse des tests.
- **Attention** : Une couverture élevée ne garantit pas l'absence de bugs. La qualité des tests est primordiale.

---

## La pyramide des tests

La pyramide des tests est une stratégie qui illustre la proportion recommandée de chaque type de test dans un projet logiciel :

1. **Base : Tests Unitaires**
   - La plus grande partie des tests.
   - Faciles, rapides, et peu coûteux à mettre en place.

2. **Milieu : Tests d'Intégration**
   - Moins nombreux que les tests unitaires.
   - Vérifient la cohérence entre différents modules ou services.

3. **Sommet : Tests Fonctionnels (ou End-to-End)**
   - Peu nombreux.
   - Plus longs et coûteux à exécuter, mais essentiels pour valider le comportement global.

Cette pyramide aide à maintenir un bon équilibre entre effort, coût et couverture.

---

## Les doubles de Test
Les doubles de test sont des objets utilisés pour simuler des dépendances externes dans les tests. Ils permettent d'isoler l'unité de code testée.

- **Types principaux** :
  - **Mocks** : Simulent le comportement attendu d'une dépendance et vérifient si elle a été utilisée correctement.
  - **Fakes** : Fournissent une implémentation simplifiée ou alternative.
  - **Stubs** : Retourner des valeurs préprogrammées en réponse à des appels spécifiques.
  - **Spies** : Surveillent et enregistrent les interactions avec une dépendance sans modifier son comportement.

## Arrange, Act, Assert
Le principe AAA est une structure simple et claire pour écrire des tests unitaires ou d'intégration :

1. **Arrange** : Préparer l'état initial :

   - Configurer les données nécessaires.
   - Mettre en place les doubles de test (mocks, stubs, etc.) si nécessaire.
   - Initialiser les objets ou services à tester.

2. **Act** : Exécuter l'action ou le comportement à tester :

   - Appeler une méthode.
   - Exécuter une requête ou une action utilisateur simulée.

3. **Assert** : Vérifier que le résultat obtenu est conforme aux attentes :

   - Comparer les valeurs obtenues et attendues.
   - Vérifier que certaines méthodes ont été appelées ou non (mock verification).

### Pourquoi AAA ?

- **Clarté** : Le test est structuré et facile à comprendre.
- **Lisibilité** : Facilite la distinction entre la préparation, l'action, et la validation.
- **Modularité** : Chaque étape est indépendante et peut être révisée séparément.

---

## Les méthodes et bonnes pratiques autour des tests

### 1. **TDD (Test-Driven Development)**
TDD est une méthode stricte où le développement est guidé par les tests. Son cycle se compose de trois étapes :

1. **Red** : Créez un test qui échoue.
2. **Green** : Écrivez juste assez de code pour que le test passe.
3. **Refactor** : Améliorez le code sans changer son comportement.

- **Objectif** : Éviter le sur-développement et garantir que chaque fonctionnalité répond à un besoin précis.

### 2. **Test First**
Cette approche consiste à écrire les tests avant de coder. Elle permet de :
- Formaliser les exigences avant de commencer le développement.
- Clarifier ce que le code doit faire.

Contrairement à TDD, Test First ne suit pas un cycle strict et peut être utilisé comme une étape exploratoire pour poser des attentes.

### 3. **BDD (Behavior-Driven Development)**
BDD se concentre sur le comportement attendu du système en utilisant un langage naturel compréhensible par les développeurs, testeurs et parties prenantes.

- **Différences avec TDD** :
  - Pas de cycle red-green-refactor.
  - Se concentre sur la compréhension métier et le comportement utilisateur.

---

# Présentations

- [Les tests en informatique](https://docs.google.com/presentation/d/1fRxXk4yR4XuKED9eo88rSODm4kQa4olMROTbbhiMYxU)
- [Les Tests en PHP et JS](https://docs.google.com/presentation/d/1cu6BTMzV2lbArfYfJP3wSHRq29OSEimgpje2ORA-4Lw)

# Exercices

- [Exercices PHP](https://github.com/G404-CDA/Exercices-test)
- [Exercices JS](https://github.com/G404-CDA/Exercices-tests-js)
- [TP Test Suite](./TP-Test-Suite.md)

# Ressources
#### 📽️ Vidéos

- [Grafikart - PHPUnit](https://grafikart.fr/tutoriels/phpunit)
- [Moquerie - Framework moqueur]()
- [Playlist Testing All The Thing](https://www.youtube.com/watch?v=04FzlrMKPTM&list=PLtFquUj7IL8V8Ih7PGWqQb8tnldag6nz8)
- [Tester avec Laravel](https://www.youtube.com/watch?v=_MJmU-wRwpI)
- [Tester avec Symfony](https://www.youtube.com/watch?v=ukocHoa8y3o)
- [Apprendre les tests avec laravel](https://www.youtube.com/watch?v=q0HbDiScaRM)

#### 📖 Ressources

- ♨️ [Open Classroom](https://openclassrooms.com/fr/courses/4087056-testez-unitairement-votre-application-php-symfony/7828665-faites-vos-premiers-pas-avec-phpunit-et-les-tests-unitaires)

- [Mockery Tips](https://darkghosthunter.medium.com/php-10-tips-to-use-for-mockery-33673ba01321)

- [L'art de Mocker en TDD](https://blog.bitsrc.io/the-art-of-mocking-in-tdd-d81edf9f8f02)

- [Mockery CheatSheet](https://github.com/minutephp/mockery-cheat-sheet)

- [Stub vs Mock](https://www.turing.com/kb/stub-vs-mock)

- [Toutes les CheatSheets du monde](https://medium.com/level-up-web/the-best-cheat-sheets-guides-docs-for-web-designers-and-web-developers-8e335a0aad77)
- [PhpUnit CheatSheeeeeeeeet](https://gist.github.com/loonies/1255249)

#### 🧙Ressources intéressantes

- [Awesome PHP](https://github.com/ziadoz/awesome-php#testing)
- [TDD en PHP](https://github.com/unicodeveloper/awesome-tdd#tdd-in-php)
