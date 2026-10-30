# Outils météo

Outils météo gratuits : **Météo à venir** et **Météo trajet**.

Le générateur de fiche climat communale a déménagé dans le dépôt privé `climat-mairies` (site https://climat-mairies.fr).

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | Page d'accueil des deux outils |
| `meteo-future.html` | Prévisions 16 jours d'une commune, normales, tendance saisonnière, horizon neige |
| `meteo-trajet.html` | Météo jour par jour le long d'un trajet : étapes (commune, date d'arrivée, altitude), graphe T° mini/maxi, pluie/neige, bulletin rédigé, PDF A4 |
| `logo-fef73.jpg` | Avatar de la signature de bas de page |
| `LICENSE` | Droits d'auteur (tous droits réservés) |
| `README.md` | Ce fichier |

## Météo trajet (`meteo-trajet.html`)

Page : https://fef73.github.io/mairies-pdf/meteo-trajet.html.

Le temps prévu jour par jour le long d'un voyage, à chaque étape.

### Utilisation

1. Saisir les étapes (jusqu'à 10) : commune choisie dans la liste, date d'arrivée, et en option l'heure d'arrivée et l'altitude.
2. Cliquer sur **Afficher**.
3. Sous le graphique, un **bulletin** rédigé (temps par étape, résumé, quoi emporter), à copier avec **📋 Copier**.
4. Facultatif : **PDF / Imprimer** (A4 paysage, bulletin inclus), ou partager l'adresse de la page, qui contient tout le trajet.

### Graphique

- Une colonne par jour : le jour d'arrivée à chaque étape, les jours sur place jusqu'à l'étape suivante, puis la suite des prévisions de la dernière étape jusqu'à J+15.
- Températures maxi (orange) et mini (bleu), pluie et neige en barres, icône du temps.
- ◆ Température à l'heure d'arrivée, si elle est saisie.
- Pastille de qualité de l'air : indice européen, maximum du jour (prévision d'environ 5 jours).
- Au-delà de 7 jours, fond grisé : simple tendance.
- Clic sur une commune : ses prévisions détaillées dans `meteo-future.html`.

### Enregistrer un trajet

**💾 Enregistrer** télécharge le trajet dans un fichier `trajet_….json` ; **📂 Ouvrir** le recharge. Les dates y sont stockées en jours depuis le départ (`"jour": 0, 2, 3…`) : à l'ouverture, choisir la date de départ puis **Recaler les dates**. Format : `{"format":"meteo-trajet","version":1,"nom":…,"etapes":[{"insee","nom","dep","lat","lon","jour","heure","altitude"}]}`.

### Adresse de la page

`?e=INSEE_date[_altitude[_HH:MM]],…` — exemple : `?e=73065_2026-10-16__14:30,11262_2026-10-18_150`.
Ouverte avec `?lat=…&lon=…` (lien du menu avec « Ma position »), la première étape est préremplie avec la commune correspondante.

### Données

- Prévisions : [Open-Meteo](https://open-meteo.com/) (Météo-France, ECMWF…), corrigées à l'altitude choisie.
- Qualité de l'air : Copernicus CAMS via Open-Meteo.
- Communes : geo.api.gouv.fr (point de calcul : la mairie).
- Aucune donnée n'est conservée : tout est calculé dans le navigateur.

## Un seul moteur

La fiche est calculée et dessinée par `fiche-moteur.js` et `fiche-moteur.css`. La page commune publique de mairies-offres (`commune.html?insee=…`, mode kiosque) charge les mêmes fichiers : une correction faite ici s'applique aux deux. Les pages sont publiées en clair (plus de StatiCrypt) ; une barrière légère par mot de passe reste sur les outils internes.

## Droits

© 2026 Fernand (fef73) — tous droits réservés. Voir [LICENSE](LICENSE).

---

Créé par fef73 avec [Claude](https://claude.ai).
