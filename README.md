# 💰 TipCalculator — Calculateur de pourboire

Petite application Android écrite en **Kotlin** avec **Jetpack Compose**. Elle calcule le pourboire à verser à partir d'un montant de facture et d'un pourcentage choisi par l'utilisateur.

---

## 📱 Ce que fait l'application

- L'utilisateur saisit le montant de la facture
- L'utilisateur saisit le pourcentage de pourboire voulu
- Un bouton bascule (`Switch`) permet d'arrondir le pourboire à l'entier supérieur
- Le montant du pourboire est calculé et affiché instantanément, dans le format monétaire local
- Chaque champ de saisie est précédé d'une icône (argent, pourcentage)
- L'interface reste utilisable en mode Paysage grâce à un défilement vertical (`verticalScroll`)

---

## 🏗️ Organisation du code

L'app est bâtie entièrement en **Jetpack Compose** et applique le principe de **state hoisting** :

| Composable | Rôle |
|---|---|
| `MainActivity` | Point d'entrée, initialise le thème |
| `TipTimeLayout()` | Composable racine, détient l'état (`amountInput`, `tipInput`, `roundUp`) |
| `EditNumberField()` | Champ de saisie numérique réutilisable, avec icône et label |
| `RoundTheTipRow()` | Ligne du bouton bascule d'arrondi |
| `calculateTip()` | Calcule et formate le pourboire |

L'état est stocké via `remember { mutableStateOf(...) }` et exposé avec `by`, afin que Compose recompose automatiquement l'UI à chaque changement.

---

## 🛠️ Ce qu'il faut avant de commencer

- Android Studio à jour
- Kotlin
- SDK Android compatible Jetpack Compose (API 24 ou plus)
- Émulateur ou téléphone Android

---

## 🚀 Comment lancer le projet

1. Récupérez le projet (clone ou téléchargement).
2. Ouvrez-le dans Android Studio.
3. Attendez la synchronisation Gradle.
4. Assurez-vous que `res/drawable/money.xml` et `res/drawable/percent.xml` existent.
5. Cliquez sur Run pour lancer l'app.

---

## 🎓 Cadre du projet

Ce projet suit l'atelier « Calculer un pourboire personnalisé » du chapitre 8 :
- Ajout d'un bouton bascule
- Arrondi conditionnel du pourboire
- Support du mode Paysage
- Icônes dans les champs de texte
