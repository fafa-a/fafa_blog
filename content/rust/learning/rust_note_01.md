+++
title = "Rust note - 01"
description = "Introduction et concepts clés"
date = 2024-12-26
[taxonomies]
categories = ["learning","rust"]
tags = ["key-concepts","notes","threads","process","unit-type","reference-counting","smart-pointers"]
+++

## Introduction

Afin d'apprendre Rust, j'ai décidé de le lire le livre [The Rust Programming Language](https://www.amazon.com/Rust-Programming-Language-2nd/dp/1718503105) de Steve Klabnik. À ce jour (2024-12-26), je ne me souviens pas pourquoi je n'ai pas fini sa lecture. J'ai acheté plus tard le livre [rust in action](https://www.amazon.com/Rust-Action-TS-McNamara/dp/1617294551) de Tim McNamara, car dans un article listant des livres pour apprendre `Rust`, il était bien classé et sa description m'a plu.

Au moment où je commence le blog, j'ai déjà quelques notes sur le livre, j'en suis à la page 42/456 😅. Les notes que je prends sont plus des mémos que des notes de cours. Pour le blog il se peut que je me motive et fasse des phrases. Les notes ne seront pas que sur le langage Rust mais peut-être aussi sur des interrogations lors de la lecture des livres ou de la realisation de projets.  

La premiere note est juste des questions que j'ai posées a une IA sur des concepts clés.

## **Concepts Clés :**

### **Threads**

- **Plus Petite Unité d'Exécution** : Un thread est la plus petite séquence d'instructions programmées qui peut être gérée par le planificateur du système d'exploitation.
- **Exécution Concurrente** : Permet à plusieurs threads de s'exécuter simultanément, améliorant ainsi les performances.
- **Ressources Partagées** : Les threads au sein du même processus partagent la mémoire et les ressources.
- **Pile d'Exécution Individuelle** : Chaque thread a sa propre pile, mais partage la mémoire heap.
- **Utilisation dans les Systèmes Multicœurs** : Idéal pour l'exécution parallèle sur des systèmes multicœurs.

### **Processus**

- **Instance de Programme** : Une instance en cours d'exécution d'un programme.
- **Isolation de Mémoire** : Fonctionne dans son propre espace mémoire, isolé des autres processus.
- **Contient des Threads** : Un processus peut contenir plusieurs threads, qui sont ses unités exécutables.
- **Communication Inter-Processus** : Utilise des méthodes IPC pour communiquer avec d'autres processus.
- **Consommation de Ressources** : Nécessite plus de ressources que la gestion des threads.
- **Géré par le Système d'Exploitation** : Géré par le système d'exploitation pour la création, la planification et la terminaison.

### **Unit type**

- **Description** : Le type unit en Rust, noté **`()`**, est un type de taille zéro qui signifie 'pas de valeur'.
- **Utilisation** : Couramment utilisé comme type de retour pour les fonctions qui ne retournent pas de valeur significative.
- **Comparaison** : Semblable à **`void`** en C/C++, mais en Rust, **`()`** est un type réel et peut être utilisé là où des types sont requis.
- **Fonctionnalité** : Dans les fonctions, **`return;`** ou l'absence de déclaration de retour renvoie implicitement **`()`**.

### **Reference counting**

- **Technique de Gestion de Mémoire** : Gère la durée de vie des objets à travers des comptes de références.
- **Suivi du Compte de Références** : Compte le nombre de références à un objet.
- **Désallocation Automatique** : Un objet est désalloué lorsque le compte de références atteint zéro.
- **Prévention des Fuites de Mémoire** : Aide à la nettoyage automatique de la mémoire, évitant la gestion manuelle de la mémoire.
- **Utilisation dans les Ressources Partagées** : Utile pour gérer des structures de données et des ressources partagées.
- **Incrémentation/Décrémentation des Comptes** : Le compte de références augmente avec de nouvelles références et diminue lorsque des références sont supprimées.
- **Assistance à la Collecte des Déchets** : Simplifie les processus de collecte des déchets dans certains langages de programmation.

### **Smart pointers**

- **Gestion Automatique de la Mémoire** : Gère l'allocation et la désallocation de la mémoire.
- **Contrôle des Ressources** : Gère la durée de vie des objets, prévenant les fuites de mémoire.
- **Sémantique de Propriété** : Définit des règles pour la propriété des objets (unique ou partagée).
- **Durées de Vie Scoped** : Assure le nettoyage lors de la sortie de portée.
- **Utilisation dans des Structures Complexes** : Idéal pour gérer des ressources dans des structures de données complexes.
- **Sécurité Améliorée** : Réduit les erreurs comme les pointeurs pendants.
- **Gestion de la Charge** : Plus gourmand en ressources que les pointeurs bruts.
- **Implémentation dans le Langage** : Commun en C++, Rust et d'autres langages sans collecte des déchets.
