# fredcom

Projet Symfony développé en équipe avec un environnement local simple, lisible et reproductible.

Ce README explique **quoi faire**, mais surtout **pourquoi** chaque étape existe.

---

## 🧠 Principe fondamental du projet

👉 **Toutes les commandes doivent être exécutées depuis la racine du projet.**

La *racine du projet* est le dossier `fredcom/` créé par Git lors du clonage.

Une fois placé dans ce dossier, **on n’en sort plus** pour travailler sur le projet.

---

## 🧰 Stack technique

- PHP 8.2
- Symfony (LTS)
- Symfony CLI (serveur local)
- Doctrine ORM
- MySQL 8 (Docker)
- phpMyAdmin (Docker)
- Git + GitHub
- Docker Desktop (WSL2 sous Windows)

---

## 📦 Prérequis (à installer UNE FOIS)

Ces outils doivent être installés **avant de commencer** :

- Git
- PHP ≥ 8.2
- Composer
- Docker Desktop
- Symfony CLI

> 💡 Ces outils ne font **pas partie du projet**, ils permettent de le faire tourner.

---

## 🚀 Installation du projet (pas à pas)

### 1️⃣ Récupérer le projet (Git)

```bash
git clone https://github.com/<organisation-ou-user>/fredcom.git
