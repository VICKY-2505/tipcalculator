# TipTime - Tip Calculator 💰

Une application Android moderne et intuitive qui permet de calculer rapidement le montant d'un pourboire en fonction du montant de la facture et de la qualité du service. Ce projet a été développé en utilisant **Android Studio** et le framework moderne **Jetpack Compose**.

## ✨ Fonctionnalités

*   **Calcul dynamique :** Le montant du pourboire se met à jour instantanément à chaque saisie.
*   **Pourcentage personnalisé :** Saisie libre du pourcentage de pourboire souhaité.
*   **Arrondi intelligent :** Une option (Switch) permet d'arrondir automatiquement le montant du pourboire à l'entier supérieur.
*   **Interface adaptative :** Support du défilement vertical (`verticalScroll`) pour garantir une navigation fluide sur tous les écrans, même avec le clavier ouvert.
*   **Design Moderne :** Intégration d'icônes visuelles (`leadingIcon`) pour une meilleure expérience utilisateur.
*   **Localisation :** Formatage automatique du résultat selon la devise locale du système ($10.00, 10,00 €, etc.).

## 🛠️ Technologies & Outils utilisés

*   **Langage :** [Kotlin](https://kotlinlang.org)
*   **UI Framework :** [Jetpack Compose](https://android.com) (Material Design 3)
*   **Gestion des états :** `remember { mutableStateOf(...) }` pour une UI réactive.
*   **Outils d'architecture :** State Hoisting (remontée d'état) pour les composants réutilisables (`EditNumberField`, `RoundTheTipRow`).

## 📸 Aperçu du Code Architectural

L'application suit les principes recommandés par Google pour la séparation des composants d'interface :

```kotlin
// Exemple de composant réutilisable avec icône et gestion de clavier
@Composable
fun EditNumberField(
    @StringRes label: Int,
    @DrawableRes leadingIcon: Int,
    keyboardOptions: KeyboardOptions,
    value: String,
    onValueChange: (String) -> Unit,
    modifier: Modifier = Modifier
) {
    TextField(
        value = value,
        leadingIcon = { Icon(painterResource(id = leadingIcon), null) },
        onValueChange = onValueChange,
        label = { Text(stringResource(label)) },
        singleLine = true,
        keyboardOptions = keyboardOptions,
        modifier = modifier
    )
}
```

## 🚀 Comment lancer le projet ?

1.  Clonez ce dépôt sur votre machine locale.
2.  Ouvrez le projet avec **Android Studio** (version Hedgehog ou ultérieure recommandée).
3.  Laissez Gradle synchroniser les dépendances.
4.  Lancez l'application sur un **Émulateur** ou un **appareil Android physique** (API 24 minimum).

---
Développé avec ❤️ dans le cadre de l'apprentissage de Jetpack Compose.
