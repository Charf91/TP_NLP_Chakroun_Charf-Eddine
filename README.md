# Mini-Transformer en 4 TP

Quatre notebooks qui reconstruisent pas à pas un petit modèle de langage au niveau caractère, entraîné sur Tiny Shakespeare.

| Notebook | Contenu |
|---|---|
| `TP1_donnees_et_bigramme.ipynb` | Tokenisation caractère par caractère, construction des paires contexte/cible et des mini-batchs, modèle bigramme, génération avant et après entraînement. |
| `TP2_auto_attention.ipynb` | De la moyenne causale à une tête d'auto-attention (Q, K, V, masque, Softmax, mise à l'échelle par √d_h). |
| `TP3_layernorm_et_mlp.ipynb` | LayerNorm codée à la main et validée contre PyTorch, MLP C → 4C → C, connexion résiduelle. |
| `TP4_modele_complet.ipynb` | Assemblage complet : multi-têtes, blocs, embeddings de position, entraînement, génération de texte et expériences. |

## Lancer les notebooks

1. Ouvrir le notebook dans [Google Colab](https://colab.research.google.com) (*Fichier → Importer le notebook*).
2. Pour le TP 4, activer le GPU : *Exécution → Modifier le type d'exécution → GPU*.
3. Exécuter les cellules dans l'ordre (*Exécution → Tout exécuter*).

Chaque notebook est indépendant et télécharge lui-même le corpus `input.txt`.

**Dépendances :** Python 3, PyTorch, matplotlib (déjà installés dans Colab).

**Durée indicative :** quelques secondes pour les TP 2 et 3, environ une minute pour le TP 1, et quelques minutes sur GPU pour le TP 4. Sur CPU, réduire `max_iters` et `exp_iters` dans le TP 4.

## Résultats principaux

| Modèle | Loss de validation |
|---|---|
| Prédiction uniforme (ln 65) | 4,17 |
| Bigramme (TP 1) | ≈ 2,3–2,5 |
| Mini-Transformer, 4 blocs, 0,21 M paramètres (TP 4) | **1,82** |

Le texte généré par le modèle du TP 4 reprend la structure d'une pièce de théâtre (noms de personnages, répliques) avec de vrais mots anglais, sans pour autant produire de phrases correctes.
