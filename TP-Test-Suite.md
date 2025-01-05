# TP : Appliquer des tests automatisés à votre projet perso 🚀

Ce TP vous permettra de mettre en pratique les concepts liés aux tests automatisés sur votre projet personnel. Vous utiliserez des outils spécifiques pour tester une nouvelle fonctionnalité de bout en bout sur votre backend.

---

## Objectif du TP 🎯

Vous devez implémenter une nouvelle fonctionnalité (ou compléter une existante) dans votre projet Laravel. L'objectif est d'appliquer différents types de tests pour garantir la robustesse et la fiabilité de votre application.

---

## Étapes à suivre 📋

### 1. **Choisir une fonctionnalité à implémenter**

- Identifiez une fonctionnalité que vous n'avez pas encore développée (ou inventez-en une nouvelle).
- Assurez-vous qu'elle inclut une logique métier et des interactions utilisateur.

---

### 2. **Décrire la fonctionnalité en BDD** 

- Utilisez **Behat** pour écrire des scénarios décrivant la fonctionnalité en langage naturel (Gherkin).
- Décrivez le comportement attendu sous forme de scénarios clairs et compréhensibles.



---

### 3. **Implémenter la logique métier en TDD** 🛠️

Suivez la méthodologie **TDD** pour chaque partie de la logique métier de votre fonctionnalité. Respectez les trois règles du TDD :

1. **Écrivez uniquement le code de production nécessaire pour passer un test unitaire qui échoue.**
2. **N'écrivez un test que s'il échoue initialement (une erreur de compilation est un échec).**
3. **N'écrivez pas plus de code de production que nécessaire pour faire passer le test.**

- Utilisez **PHPUnit** pour écrire des tests unitaires.
- Ne faites pas de TDD pour les parties CRUD classiques.



---

### 4. **Tester les parties CRUD avec des tests d'intégration** 🔄

- Mettez en place des tests d'intégration pour les opérations CRUD associées à votre fonctionnalité.
- Ces tests doivent vérifier la cohérence des interactions entre les différents composants (base de données, contrôleurs, etc.).



---

### 5. **Vérifier la fonctionnalité avec un test BDD** ✅

- Une fois que la logique métier et les opérations CRUD sont implémentées, exécutez vos scénarios BDD avec Behat.
- Assurez-vous que tous les scénarios passent avec succès.

---

### 6. **Créer un test End-to-End** 🌍

- Implémentez au moins un test End-to-End pour valider la fonctionnalité dans son ensemble.
- Utilisez **Dusk** pour écrire ce test fonctionnel.
- Ce test doit simuler un parcours utilisateur complet (par exemple, de la soumission du formulaire à la validation du résultat).



---

## Résultats attendus 🎉

À la fin de ce TP, vous devez avoir :

1. Des scénarios BDD décrivant la fonctionnalité.
2. Une logique métier implémentée en TDD avec des tests unitaires complets.
3. Des tests d'intégration pour les opérations CRUD.
4. Un test End-to-End validant la fonctionnalité dans son ensemble.
5. Tous les tests qui passent avec succès.

