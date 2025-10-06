# Copilot Instructions for 09-mots-langue-francaise

## Vue d'ensemble
Ce projet manipule un corpus de mots français (fichier `corpus.txt`, ~336 000 mots) via des fonctions Python dans `main.py`. Les fonctions principales sont :
- `read_data(filename)`: lit le fichier et retourne une liste de mots (une par ligne).
- `ensemble_mots(filename)`: retourne un set de mots pour des recherches rapides.
- `mots_de_n_lettres(mots, n)`: extrait les mots de longueur n.
- `mots_avec(mots, s)`: extrait les mots contenant une chaîne donnée.
- `cherche1` et `cherche2`: recherches avancées sur le corpus.

## Convention et architecture
- Toutes les fonctions secondaires sont définies dans `main.py`.
- La fonction `main()` sert à tester les fonctions secondaires et à afficher les résultats.
- Les appels à `main()` sont protégés par le bloc `if __name__ == "__main__":`.
- Les tests unitaires sont intégrés sous forme de docstrings avec des exemples.

## Workflows essentiels
- **Exécution** :
  ```bash
  python main.py
  ```
- **Tests unitaires** :
  ```bash
  pytest .python
  ```
- **Qualité du code** :
  ```bash
  pylint main.py
  ```
- **Git workflow** :
  ```bash
  git add .
  git commit -m "message explicatif"
  git push
  ```

## Points spécifiques
- Utiliser `ensemble_mots()` pour les recherches avec l'opérateur `in` (complexité O(1)).
- Pour extraire des mots de longueur spécifique, utiliser `mots_de_n_lettres()` sur le set retourné par `ensemble_mots()`.
- Pour des échantillons aléatoires, utiliser `random.sample()` sur le set ou la liste.
- Les fonctions doivent éviter la duplication de code (ex : `ensemble_mots()` doit utiliser `read_data()`).
- Les conventions de nommage sont en français.

## Exemples d'utilisation
- Vérifier la présence d'un mot :
  ```python
  ens = ensemble_mots("corpus.txt")
  print("chronophage" in ens)
  ```
- Nombre de mots de 7 lettres :
  ```python
  mots7 = mots_de_n_lettres(ens, 7)
  print(len(mots7))
  print(random.sample(list(mots7), 5))
  ```

## Fichiers clés
- `main.py` : toutes les fonctions et la logique principale
- `corpus.txt` : source des mots
- `README.md` : consignes et exemples

## Bonnes pratiques
- Tester chaque fonction via `main()` avant d'ajouter des tests unitaires.
- Respecter les conventions de nommage et la structure du projet.
- Utiliser les exemples du README pour guider l'implémentation et les tests.

---

Pour toute ambiguïté ou règle manquante, se référer au README ou demander une clarification à l'utilisateur.
