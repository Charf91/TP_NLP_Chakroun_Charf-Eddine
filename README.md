# Mini-Transformer en 4 TP

Quatre notebooks qui reconstruisent pas à pas un petit modèle de langage au niveau caractère, entraîné sur Tiny Shakespeare.

| Notebook | Contenu |
|---|---|
| `TP1_donnees_et_bigramme.ipynb` | Tokenisation caractère par caractère, construction des paires contexte/cible et des mini-batchs, modèle bigramme, génération avant et après entraînement. |
| `TP2_auto_attention.ipynb` | De la moyenne causale à une tête d'auto-attention (Q, K, V, masque, Softmax, mise à l'échelle par √d_h). |
| `TP3_layernorm_et_mlp.ipynb` | LayerNorm codée à la main et validée contre PyTorch, MLP C → 4C → C, connexion résiduelle. |
| `TP4_modele_complet.ipynb` | Assemblage complet : multi-têtes, blocs, embeddings de position, entraînement, génération de texte et expériences. |


## Résultats principaux

| Modèle | Loss de validation |
|---|---|
| Prédiction uniforme (ln 65) | 4,17 |
| Bigramme (TP 1) | ≈ 2,3–2,5 |
| Mini-Transformer, 4 blocs, 0,21 M paramètres (TP 4) | **1,82** |

Le texte généré par le modèle du TP 4 reprend la structure d'une pièce de théâtre (noms de personnages, répliques) avec de vrais mots anglais, sans pour autant produire de phrases correctes.
