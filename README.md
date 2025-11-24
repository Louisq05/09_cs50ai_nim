# Nim — Reinforcement Learning AI

**CS50AI — Project: Nim**  
**Python version required:** 3.12

## 📌 Description

Ce projet consiste à écrire une **intelligence artificielle capable d’apprendre à jouer au jeu de Nim**, en utilisant le **Q-learning**, une méthode d’apprentissage par renforcement.  
En jouant des milliers de parties contre elle-même, l’IA apprend progressivement quelles actions mènent à la victoire et lesquelles mènent à la défaite.

## 🧠 Objectif

Implémenter une IA qui :

- apprend seule à jouer à Nim via Q-learning ;
- calcule et met à jour des valeurs Q(s, a) pour les couples état/action ;
- choisit ses actions selon une stratégie **ε-greedy** ;
- devient de plus en plus performante au fil des entraînements.

---

## 🚀 Exécution

### 🎮 Entraîner puis jouer contre l’IA

```
bash 
python play.py 
Playing training game 1 
... 
Playing training game 10000 Done training  
Piles: 
Pile 0: 1 
Pile 1: 3 
Pile 2: 5 
Pile 3: 7  
AI's Turn 
AI chose to take 1 from pile 2.
```

---

## 🗂️ Structure du Projet

- **nim.py** — Contient les classes `Nim` et `NimAI` (logique du jeu + IA).
- **play.py** — Lancement de l’entraînement et du jeu humain contre IA.

---

## 📚 Contexte : le jeu de Nim

- Le jeu commence avec plusieurs piles contenant chacune un certain nombre d’objets.
- À chaque tour, un joueur peut retirer autant d'objets qu’il veut, mais **dans une seule pile**.
- **Celui qui prend le dernier objet perd.**

---

## 🔍 Principe du Q-Learning

Chaque action dans une situation donnée reçoit une "valeur" Q :

$$Q(s, a) ← Q(s, a) + α * ( [reward + future_rewards] - Q(s, a) )$$

- **s** : état (configuration actuelle des piles)
- **a** : action (pile i, retirer j objets)
- **reward** :
    - +1 si l’action mène à une victoire
    - -1 si elle mène à une défaite
    - 0 si le jeu continue
- **alpha (α)** : taux d’apprentissage
- **epsilon (ε)** : probabilité de jouer un coup aléatoire (exploration)

---

## 🙏 Remerciements

Projet tiré du programme CS50’s Introduction to Artificial Intelligence with Python — Harvard University.