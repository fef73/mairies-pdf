# Générateur de fiche climat communale

Outil à usage interne qui produit une **fiche climat A4** (ou A3) pour une commune : normales 1991–2020, écart de l'année en cours, extrêmes et évolution depuis 1950, à l'altitude choisie. Export en PDF par l'impression du navigateur.

Page : https://fef73.github.io/mairies-pdf/ — proposition commerciale : [mairies-offres](https://fef73.github.io/mairies-offres/).

## Utilisation

1. Taper le nom de la commune et la choisir dans la liste (option « France uniquement »).
2. Facultatif : altitude en mètres, logo ou blason de la commune, couleur, format A4 ou A3, mention de pied de page, bloc « Quand venir ».
3. Cliquer sur **Générer**, puis sur **PDF / Imprimer** (« Enregistrer au format PDF »).

## Contenu de la fiche

- En-tête : commune, département, altitude, population, logo.
- Climogramme mensuel (températures min et max, pluie) et quatre chiffres clés : température moyenne, pluie, neige, ensoleillement.
- Année en cours face à la normale : écart de température et de précipitations sur la même fenêtre calendaire.
- Bande de couleurs « un trait par année » depuis 1950 et tableau des jours chauds, de gel, de forte pluie et de neige sur trois périodes.
- Extrêmes depuis 1950 avec leurs dates, repères locaux rédigés automatiquement, option « Quand venir ».

## Données et limites

- Réanalyse ERA5 (Copernicus / ECMWF) via [Open-Meteo](https://open-meteo.com/) : 1950 jusqu'à il y a 6 jours, en trois requêtes. Géocodage Open-Meteo.
- Valeurs **modélisées** au point et à l'altitude choisis : elles peuvent différer d'une station. Document informatif, il ne remplace pas la vigilance Météo-France.
- L'usage commercial d'Open-Meteo nécessite un abonnement payant.
- Aucune donnée n'est conservée : tout est calculé dans le navigateur.

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | Le générateur complet (HTML, CSS et JavaScript) |
| `meteo-future.html` | Prévisions 16 jours d'une commune, normales, tendance saisonnière, horizon neige |
| `meteo-trajet.html` | Météo jour par jour le long d'un trajet : étapes (commune, date d'arrivée, altitude), graphe T° mini/maxi, pluie/neige, PDF A4 |
| `logo-fef73.jpg` | Avatar de la signature de bas de page |
| `LICENSE` | Droits d'auteur (tous droits réservés) |
| `README.md` | Ce fichier |

## Droits

© 2026 Fernand (fef73) — tous droits réservés. Voir [LICENSE](LICENSE).

---

Créé par fef73 avec [Claude](https://claude.ai).
