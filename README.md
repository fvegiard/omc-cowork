# omc-cowork

Marketplace claude.ai/Cowork pour oh-my-claudecode : pointe vers la branche `cowork` (sans `bin/`) de `fvegiard/oh-my-claudecode`.

## Commit attendu dans le cloud

| Date (UTC) | Commit de `fvegiard/oh-my-claudecode@cowork` | Contenu |
| :- | :- | :- |
| 2026-11-16 | `00e5f199069ab5c933e8a226c43b55372d2e0a00` | pont shell `scripts/cowork-mcp.cjs` + skill `omc-tools` |

## Règle de resynchronisation

claude.ai resynchronise un marketplace quand on pousse sur la branche par défaut du dépôt **marketplace** (ici `main`), pas quand on pousse sur le dépôt source du plugin. Référence : https://claude.com/docs/plugins/org-sync (lu le 2026-11-16 ; la page décrit la synchro d'organisation, son application à un marketplace de compte est une inférence).

Après chaque push sur `fvegiard/oh-my-claudecode@cowork` :

1. Mettre à jour la ligne du tableau ci-dessus avec le nouveau commit et pousser sur `main`.
2. Si la synchro automatique n'est pas active, lancer la synchro du marketplace à la main dans claude.ai.
3. Vérifier dans une **nouvelle** session cloud que le skill `oh-my-claudecode:omc-tools` est listé.

## Vérification du pont (2026-11-16, session cloud)

Depuis un clone de `cowork` à `00e5f19` : `node scripts/cowork-mcp.cjs list` retourne 50 outils, code de sortie 0. `call notepad_write_working` et `call state_list_active` : code de sortie 0.
