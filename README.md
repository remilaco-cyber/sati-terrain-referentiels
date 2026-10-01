# sati-terrain-referentiels

Référentiels espèces et engins pour l'application **SATI Terrain** (fiche de
contrôle pêche, onglet "Contrôle Pro"), synchronisables directement depuis
l'écran *Options & maintenance* de l'application :

- `especes.json` — code FAO alpha-3, nom français, nom scientifique, taille
  minimale réglementaire (cm, indicative — toujours vérifier le texte en
  vigueur avant verbalisation).
- `engins.json` — code FAO alpha-3, nom français, catégorie principale.

## Format attendu

`especes.json` : tableau d'objets
```json
{"code_alpha3": "BFT", "nom_francais": "Thon rouge", "nom_scientifique": "Thunnus thynnus", "taille_minimale_reglementaire": null}
```

`engins.json` : tableau d'objets
```json
{"code_alpha3": "OTB", "nom_francais": "Chalut de fond à panneaux", "categorie_principale": "Chaluts"}
```

Seuls `code_alpha3` et `nom_francais` sont obligatoires ; les autres champs
peuvent être `null` ou omis.

## Utilisation dans l'application

Dans SATI Terrain → bouton *Options* → *Référentiels FAO* → renseigner les
deux URL "brutes" GitHub ci-dessous → *Vérifier et mettre à jour les codes
FAO* :

- `https://raw.githubusercontent.com/<compte>/sati-terrain-referentiels/main/especes.json`
- `https://raw.githubusercontent.com/<compte>/sati-terrain-referentiels/main/engins.json`

L'application reste utilisable hors ligne avec son jeu de données embarqué
même sans synchronisation.

## Mettre à jour les données

Modifier `especes.json` / `engins.json`, committer, pousser — la prochaine
synchronisation depuis l'application reprendra automatiquement le contenu à
jour (pas de workflow GitHub Actions nécessaire, ce sont de simples fichiers
statiques).
