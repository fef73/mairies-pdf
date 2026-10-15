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

## Météo trajet (`meteo-trajet.html`)

Page : https://fef73.github.io/mairies-pdf/meteo-trajet.html — aussi accessible depuis le menu de [comparateur-meteo.fr](https://comparateur-meteo.fr).

Le temps prévu jour par jour le long d'un voyage, à chaque étape.

### Utilisation

1. Saisir les étapes (jusqu'à 10) : commune choisie dans la liste, date d'arrivée, et en option l'heure d'arrivée et l'altitude.
2. Cliquer sur **Afficher**.
3. Facultatif : **PDF / Imprimer** (A4 paysage), ou partager l'adresse de la page, qui contient tout le trajet.

### Graphique

- Une colonne par jour : le jour d'arrivée à chaque étape, les jours sur place jusqu'à l'étape suivante, puis la suite des prévisions de la dernière étape jusqu'à J+15.
- Températures maxi (orange) et mini (bleu), pluie et neige en barres, icône du temps.
- ◆ Température à l'heure d'arrivée, si elle est saisie.
- Pastille de qualité de l'air : indice européen, maximum du jour (prévision d'environ 5 jours).
- Au-delà de 7 jours, fond grisé : simple tendance.
- Clic sur une commune : ses prévisions détaillées dans `meteo-future.html`.

### Adresse de la page

`?e=INSEE_date[_altitude[_HH:MM]],…` — exemple : `?e=73065_2026-10-16__14:30,11262_2026-10-18_150`.
Ouverte avec `?lat=…&lon=…` (lien du menu avec « Ma position »), la première étape est préremplie avec la commune correspondante.

### Données

- Prévisions : [Open-Meteo](https://open-meteo.com/) (Météo-France, ECMWF…), corrigées à l'altitude choisie.
- Qualité de l'air : Copernicus CAMS via Open-Meteo.
- Communes : geo.api.gouv.fr (point de calcul : la mairie).
- Aucune donnée n'est conservée : tout est calculé dans le navigateur.

## Droits

© 2026 Fernand (fef73) — tous droits réservés. Voir [LICENSE](LICENSE).

---

Créé par fef73 avec [Claude](https://claude.ai).
