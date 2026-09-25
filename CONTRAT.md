# CONTRAT — pesticides-achats-nappes

## Sources

### Vente et achat de produits phytopharmaceutiques
Endpoint : https://hubeau.eaufrance.fr/api/v1/vente_achat_phyto/achats/substances
- Doc sur les vente et achat de produits phytopharmaceutiques, lue le 25-09-2026 : 2013 pour la dates des achats la plus ancienne · type_territoire est obligatoire · 20000 résultats max par appel · 2 083 caractères maximum pour l'url · profondeur d'accès aux résultats est : 20000
- Appel test du 24-09-2026 : 
https://hubeau.eaufrance.fr/api/v1/vente_achat_phyto/achats/substances?type_territoire=Zone%20postale&code_territoire=28200&annee_min=2020&size=100 → 
"count": 3605
{
    "amm": "2230581",
    "annee": 2024,
    "achat_etranger": "Non",
    "classification": "CMR",
    "classification_mention": null,
    "code_cas": "74070-46-5",
    "code_substance": "1688",
    "code_territoire": "28200",
    "fonction": "Herbicide",
    "libelle_substance": "aclonifen",
    "libelle_territoire": "28200",
    "quantite": 312.0,
    "type_territoire": "Zone postale",
    "uri_substance": "http://id.eaufrance.fr/par/1688",
    "uri_territoire": "-"
},
{
    "amm": "2190173",
    "annee": 2024,
    "achat_etranger": "Non",
    "classification": "Autre",
    "classification_mention": null,
    "code_cas": "10045-86-0",
    "code_substance": "5662",
    "code_territoire": "28200",
    "fonction": "Molluscicide",
    "libelle_substance": "phosphate ferrique",
    "libelle_territoire": "28200",
    "quantite": 380.8944,
    "type_territoire": "Zone postale",
    "uri_substance": "http://id.eaufrance.fr/par/5662",
    "uri_territoire": "-"
},

Une ligne = quoi ? Une ligne = une quantité de substance par amm, substance, année, type_territoire et code_territoire  

Quel champ dit la substance, lequel dit le territoire ?
substance = "libelle_substance" exemple "aclonifen"
territoire = "code_territoire": exemple "28200"

Quel pas de temps ? le temps est par année. Nous n'avons qu'un champ année comme date : "annee": 2024

Combien de lignes pour le pays, sur une année ?
sur l'année 2020 on a 111242 résultats avec la requête ci-dessous du 25-09-2026 :
https://hubeau.eaufrance.fr/api/v1/vente_achat_phyto/achats/substances?annee_min=2020&annee_max=2020&size=5000&type_territoire=Département

### Qualité des nappes d'eau souterraine
Endpoint : https://hubeau.eaufrance.fr/api/v1/qualite_nappes/analyses
- Doc sur la qualité des nappes d'eau souterraine, lue le 25-09-2026 : 2013 pour la dates des achats la plus ancienne · type_territoire est obligatoire · 20000 résultats max par appel · 2 083 caractères maximum pour l'url · profondeur d'accès aux résultats est : 20000
- Appel test du 24-09-2026 : https://hubeau.eaufrance.fr/api/v1/qualite_nappes/analyses?code_param=1506&num_departement=28&date_debut_prelevement=2020-01-01&size=1000 →  
"count": 2130
{
    "bss_id": "BSS000TUCB",
    "code_bss": "02538X0063/FAEP",
    "urn_bss": "http://services.ades.eaufrance.fr/pointeau/BSS000TUCB",
    "precision_coordonnees": 18,
    "longitude": 1.0258147222914746,
    "latitude": 48.45026104844603,
    "altitude": "205.0",
    "code_insee_actuel": "28335",
    "nom_commune_actuel": "Saint-Éliph",
    "num_departement": "28",
    "nom_departement": "Eure-et-Loir",
    "code_region": "24",
    "nom_region": "Centre-Val de Loire",
    "code_circonscription_administrative_bassin": "03",
    "nom_circonscription_administrative_bassin": "Seine-Normandie",
    "code_bassin_dce": "H",
    "nom_bassin_dce": "La Seine et les cours d'eau côtiers normands",
    "urn_bassin_dce": "http://www.sandre.eaufrance.fr/geo/BassinDCE/FRH",
    "code_type_point_eau": 2,
    "nom_type_point_eau": "qualitometre",
    "codes_entite_hg_bdlisa": [
        "123AC01"
    ],
    "noms_entite_hg_bdlisa": [
        "Sables du Perche du Cénomanien supérieur du Bassin Parisien, bassin du Loir et de l'Eure"
    ],
    "urns_bdlisa": [
        "http://reseau.eaufrance.fr/geotraitements/bdlisa/files/entite/123AC01.pdf"
    ],
    "codes_masse_eau_rap": [
        "GG081"
    ],
    "noms_masse_eau_rap": [
        "Sables et gres du Cenomanien sarthois libres"
    ],
    "urns_masse_eau_rap": [
        "http://www.sandre.eaufrance.fr/geo/MasseDEauSouterraine/GG081"
    ],
    "codes_masse_eau_edl": [
        "GG081"
    ],
    "noms_masse_eau_edl": [
        "Sables et gres du Cenomanien sarthois libres"
    ],
    "urns_masse_eau_edl": [
        "http://www.sandre.eaufrance.fr/geo/MasseDEauSouterraine/GG081"
    ],
    "codes_reseau": [
        "0000000028",
        "0300000330",
        "0300000203"
    ],
    "noms_reseau": [
        "Réseau national de suivi au titre du contrôle sanitaire sur les eaux brutes utilisées pour la production d'eau potable",
        "Réseau de suivi de la qualité des eaux souterraines sur le département de l'Eure-et-Loir (28) (Partie AESN) ",
        "Réseau de suivi de la qualité des eaux souterraines de la Direction Seine Aval (DSAV)"
    ],
    "uris_reseau": [
        "http://id.eaufrance.fr/DC/0000000028",
        "http://id.eaufrance.fr/DC/0300000330",
        "http://id.eaufrance.fr/DC/0300000203"
    ],
    "code_type_qualito": 1,
    "nom_type_qualito": "Point d'eau unique",
    "uri_type_qualito": "http://id.eaufrance.fr/NSA/161#1",
    "code_producteur": "20006402000023",
    "nom_producteur": "SYNDICAT MIXTE DE PRODUCTION D EAU POTABLE DE LA REGION DE LA LOUPE (SIPEPREL) (20006402000023)",
    "uri_producteur": "http://id.eaufrance.fr/INT/20006402000023",
    "date_debut_prelevement": "2021-02-08T09:30:00Z",
    "code_param": 1506,
    "nom_param": "Glyphosate",
    "uri_param": "http://id.eaufrance.fr/PAR/1506",
    "code_fraction": 23,
    "nom_fraction": "Eau brute",
    "uri_fraction": "http://id.eaufrance.fr/FAN/23",
    "resultat": 0.02,
    "code_remarque_analyse": 10,
    "nom_remarque_analyse": "Résultat inférieur au seuil de quantification",
    "uri_remarque_analyse": "http://id.eaufrance.fr/NSA/155#23",
    "code_lieu_analyse": 2,
    "nom_lieu_analyse": "Laboratoire",
    "uri_lieu_analyse": "http://id.eaufrance.fr/NSA/156#2",
    "code_methode": 454,
    "nom_methode": "Chromatographie liquide haute performance / couplée à la spectrométrie de masse en tandem",
    "uri_methode": "http://id.eaufrance.fr/MET/454",
    "code_unite": "133",
    "nom_unite": "microgramme par litre",
    "symbole_unite": "µg/L",
    "uri_unite": "http://id.eaufrance.fr/URF/133",
    "code_statut_analyse": "2",
    "nom_statut_analyse": "Donnée contrôlée niveau 1",
    "uri_statut_analyse": "http://id.eaufrance.fr/NSA/416#2",
    "code_qualification": "1",
    "nom_qualification": "Correcte",
    "uri_qualification": "http://id.eaufrance.fr/NSA/414#1",
    "limite_quantification": 0.02,
    "limite_detection": 0.007,
    "seuil_saturation": null,
    "incertitude_analytique": 50.0,
    "codes_groupe_parametre": [
        "191",
        "61",
        "41",
        "95",
        "199",
        "130",
        "127",
        "203",
        "73",
        "132",
        "129",
        "211",
        "168",
        "50",
        "216",
        "31",
        "167",
        "128",
        "192",
        "96",
        "131",
        "200",
        "209",
        "134",
        "190",
        "122",
        "133",
        "137",
        "121"
    ],
    "noms_groupe_parametre": [
        "Avis relatif aux limites de quantification des couples «paramètre-matrice» de l'agrément des laboratoires effectuant des analyses dans le domaine de l'eau et des milieux aquatiques, matrice Eau douce",
        "Divers (autres organiques)",
        "Chimique",
        "Phytosanitaires",
        "Substances actives pesticides et métabolites",
        "Polluants spécifiques de l'état écologique des eaux de surface_Loire-Bretagne",
        "Polluants spécifiques de l'état écologique des eaux de surface",
        "Liste A - Phytosanitaires",
        "Paramètres classés par usage",
        "Polluants spécifiques de l'état écologique des eaux de surface_Rhône-Méditerranée",
        "Polluants spécifiques de l'état écologique des eaux de surface_Artois-Picardie",
        "Substances pertinentes à surveiller dans les eaux de surface continentales",
        "Liste des micropolluants de l'analyse régulière du contrôle de surveillance de l'état chimique des eaux souterraines_Liste_A",
        "Micropolluants organiques",
        "Liste des micropolluants de l'analyse régulière du contrôle de surveillance de l'état chimique des eaux souterraines",
        "Paramètres classés par classe",
        "Liste des micropolluants de l'analyse régulière du contrôle de surveillance de l'état chimique des eaux souterraines",
        "Polluants spécifiques de l'état écologique des eaux de surface_Adour-Garonne",
        "Avis relatif aux limites de quantification des couples «paramètre-matrice» de l'agrément des laboratoires effectuant des analyses dans le domaine de l'eau et des milieux aquatiques, matrice Eau résiduaire",
        "Herbicides",
        "Polluants spécifiques de l'état écologique des eaux de surface_Rhin-Meuse",
        "Phytosanitaires",
        "Arrêté du 26 avril 2022 modifiant l'arrêté du 25 janvier 2010 établissant le programme de surveillance de l'état des eaux en application de l'article R.212.22 du code de l'environnement",
        "Polluants spécifiques de l'état écologique des eaux de surface_Seine-Normandie",
        "Avis relatif aux limites de quantification des couples «paramètre-matrice» de l'agrément des laboratoires effectuant des analyses dans le domaine de l'eau et des milieux aquatiques",
        "Arrêté du 7 août 2015 modifiant l'arrêté du 25 janvier 2010 établissant le programme de surveillance de l'état des eaux en application de l'article R. 212-22 du code de l'environnement",
        "Polluants spécifiques de l'état écologique des eaux de surface_Corse",
        "Polluants spécifiques de l'état écologique des eaux de surface_Martinique",
        "Paramètres classés par textes réglementaires"
    ],
    "uris_groupe_parametre": [
        "http://id.eaufrance.fr/GPR/191",
        "http://id.eaufrance.fr/GPR/61",
        "http://id.eaufrance.fr/GPR/41",
        "http://id.eaufrance.fr/GPR/95",
        "http://id.eaufrance.fr/GPR/199",
        "http://id.eaufrance.fr/GPR/130",
        "http://id.eaufrance.fr/GPR/127",
        "http://id.eaufrance.fr/GPR/203",
        "http://id.eaufrance.fr/GPR/73",
        "http://id.eaufrance.fr/GPR/132",
        "http://id.eaufrance.fr/GPR/129",
        "http://id.eaufrance.fr/GPR/211",
        "http://id.eaufrance.fr/GPR/168",
        "http://id.eaufrance.fr/GPR/50",
        "http://id.eaufrance.fr/GPR/216",
        "http://id.eaufrance.fr/GPR/31",
        "http://id.eaufrance.fr/GPR/167",
        "http://id.eaufrance.fr/GPR/128",
        "http://id.eaufrance.fr/GPR/192",
        "http://id.eaufrance.fr/GPR/96",
        "http://id.eaufrance.fr/GPR/131",
        "http://id.eaufrance.fr/GPR/200",
        "http://id.eaufrance.fr/GPR/209",
        "http://id.eaufrance.fr/GPR/134",
        "http://id.eaufrance.fr/GPR/190",
        "http://id.eaufrance.fr/GPR/122",
        "http://id.eaufrance.fr/GPR/133",
        "http://id.eaufrance.fr/GPR/137",
        "http://id.eaufrance.fr/GPR/121"
    ]
},
{
    "bss_id": "BSS000TUCB",
    "code_bss": "02538X0063/FAEP",
    "urn_bss": "http://services.ades.eaufrance.fr/pointeau/BSS000TUCB",
    "precision_coordonnees": 18,
    "longitude": 1.0258147222914746,
    "latitude": 48.45026104844603,
    "altitude": "205.0",
    "code_insee_actuel": "28335",
    "nom_commune_actuel": "Saint-Éliph",
    "num_departement": "28",
    "nom_departement": "Eure-et-Loir",
    "code_region": "24",
    "nom_region": "Centre-Val de Loire",
    "code_circonscription_administrative_bassin": "03",
    "nom_circonscription_administrative_bassin": "Seine-Normandie",
    "code_bassin_dce": "H",
    "nom_bassin_dce": "La Seine et les cours d'eau côtiers normands",
    "urn_bassin_dce": "http://www.sandre.eaufrance.fr/geo/BassinDCE/FRH",
    "code_type_point_eau": 2,
    "nom_type_point_eau": "qualitometre",
    "codes_entite_hg_bdlisa": [
        "123AC01"
    ],
    "noms_entite_hg_bdlisa": [
        "Sables du Perche du Cénomanien supérieur du Bassin Parisien, bassin du Loir et de l'Eure"
    ],
    "urns_bdlisa": [
        "http://reseau.eaufrance.fr/geotraitements/bdlisa/files/entite/123AC01.pdf"
    ],
    "codes_masse_eau_rap": [
        "GG081"
    ],
    "noms_masse_eau_rap": [
        "Sables et gres du Cenomanien sarthois libres"
    ],
    "urns_masse_eau_rap": [
        "http://www.sandre.eaufrance.fr/geo/MasseDEauSouterraine/GG081"
    ],
    "codes_masse_eau_edl": [
        "GG081"
    ],
    "noms_masse_eau_edl": [
        "Sables et gres du Cenomanien sarthois libres"
    ],
    "urns_masse_eau_edl": [
        "http://www.sandre.eaufrance.fr/geo/MasseDEauSouterraine/GG081"
    ],
    "codes_reseau": [
        "0000000028",
        "0300000330",
        "0300000203"
    ],
    "noms_reseau": [
        "Réseau national de suivi au titre du contrôle sanitaire sur les eaux brutes utilisées pour la production d'eau potable",
        "Réseau de suivi de la qualité des eaux souterraines sur le département de l'Eure-et-Loir (28) (Partie AESN) ",
        "Réseau de suivi de la qualité des eaux souterraines de la Direction Seine Aval (DSAV)"
    ],
    "uris_reseau": [
        "http://id.eaufrance.fr/DC/0000000028",
        "http://id.eaufrance.fr/DC/0300000330",
        "http://id.eaufrance.fr/DC/0300000203"
    ],
    "code_type_qualito": 1,
    "nom_type_qualito": "Point d'eau unique",
    "uri_type_qualito": "http://id.eaufrance.fr/NSA/161#1",
    "code_producteur": "20006402000023",
    "nom_producteur": "SYNDICAT MIXTE DE PRODUCTION D EAU POTABLE DE LA REGION DE LA LOUPE (SIPEPREL) (20006402000023)",
    "uri_producteur": "http://id.eaufrance.fr/INT/20006402000023",
    "date_debut_prelevement": "2021-05-12T09:05:00Z",
    "code_param": 1506,
    "nom_param": "Glyphosate",
    "uri_param": "http://id.eaufrance.fr/PAR/1506",
    "code_fraction": 23,
    "nom_fraction": "Eau brute",
    "uri_fraction": "http://id.eaufrance.fr/FAN/23",
    "resultat": 0.025,
    "code_remarque_analyse": 10,
    "nom_remarque_analyse": "Résultat inférieur au seuil de quantification",
    "uri_remarque_analyse": "http://id.eaufrance.fr/NSA/155#23",
    "code_lieu_analyse": 2,
    "nom_lieu_analyse": "Laboratoire",
    "uri_lieu_analyse": "http://id.eaufrance.fr/NSA/156#2",
    "code_methode": 454,
    "nom_methode": "Chromatographie liquide haute performance / couplée à la spectrométrie de masse en tandem",
    "uri_methode": "http://id.eaufrance.fr/MET/454",
    "code_unite": "133",
    "nom_unite": "microgramme par litre",
    "symbole_unite": "µg/L",
    "uri_unite": "http://id.eaufrance.fr/URF/133",
    "code_statut_analyse": "2",
    "nom_statut_analyse": "Donnée contrôlée niveau 1",
    "uri_statut_analyse": "http://id.eaufrance.fr/NSA/416#2",
    "code_qualification": "1",
    "nom_qualification": "Correcte",
    "uri_qualification": "http://id.eaufrance.fr/NSA/414#1",
    "limite_quantification": 0.025,
    "limite_detection": 0.008,
    "seuil_saturation": null,
    "incertitude_analytique": 50.0,
    "codes_groupe_parametre": [
        "191",
        "61",
        "41",
        "95",
        "199",
        "130",
        "127",
        "203",
        "73",
        "132",
        "129",
        "211",
        "168",
        "50",
        "216",
        "31",
        "167",
        "128",
        "192",
        "96",
        "131",
        "200",
        "209",
        "134",
        "190",
        "122",
        "133",
        "137",
        "121"
    ],
    "noms_groupe_parametre": [
        "Avis relatif aux limites de quantification des couples «paramètre-matrice» de l'agrément des laboratoires effectuant des analyses dans le domaine de l'eau et des milieux aquatiques, matrice Eau douce",
        "Divers (autres organiques)",
        "Chimique",
        "Phytosanitaires",
        "Substances actives pesticides et métabolites",
        "Polluants spécifiques de l'état écologique des eaux de surface_Loire-Bretagne",
        "Polluants spécifiques de l'état écologique des eaux de surface",
        "Liste A - Phytosanitaires",
        "Paramètres classés par usage",
        "Polluants spécifiques de l'état écologique des eaux de surface_Rhône-Méditerranée",
        "Polluants spécifiques de l'état écologique des eaux de surface_Artois-Picardie",
        "Substances pertinentes à surveiller dans les eaux de surface continentales",
        "Liste des micropolluants de l'analyse régulière du contrôle de surveillance de l'état chimique des eaux souterraines_Liste_A",
        "Micropolluants organiques",
        "Liste des micropolluants de l'analyse régulière du contrôle de surveillance de l'état chimique des eaux souterraines",
        "Paramètres classés par classe",
        "Liste des micropolluants de l'analyse régulière du contrôle de surveillance de l'état chimique des eaux souterraines",
        "Polluants spécifiques de l'état écologique des eaux de surface_Adour-Garonne",
        "Avis relatif aux limites de quantification des couples «paramètre-matrice» de l'agrément des laboratoires effectuant des analyses dans le domaine de l'eau et des milieux aquatiques, matrice Eau résiduaire",
        "Herbicides",
        "Polluants spécifiques de l'état écologique des eaux de surface_Rhin-Meuse",
        "Phytosanitaires",
        "Arrêté du 26 avril 2022 modifiant l'arrêté du 25 janvier 2010 établissant le programme de surveillance de l'état des eaux en application de l'article R.212.22 du code de l'environnement",
        "Polluants spécifiques de l'état écologique des eaux de surface_Seine-Normandie",
        "Avis relatif aux limites de quantification des couples «paramètre-matrice» de l'agrément des laboratoires effectuant des analyses dans le domaine de l'eau et des milieux aquatiques",
        "Arrêté du 7 août 2015 modifiant l'arrêté du 25 janvier 2010 établissant le programme de surveillance de l'état des eaux en application de l'article R. 212-22 du code de l'environnement",
        "Polluants spécifiques de l'état écologique des eaux de surface_Corse",
        "Polluants spécifiques de l'état écologique des eaux de surface_Martinique",
        "Paramètres classés par textes réglementaires"
    ],
    "uris_groupe_parametre": [
        "http://id.eaufrance.fr/GPR/191",
        "http://id.eaufrance.fr/GPR/61",
        "http://id.eaufrance.fr/GPR/41",
        "http://id.eaufrance.fr/GPR/95",
        "http://id.eaufrance.fr/GPR/199",
        "http://id.eaufrance.fr/GPR/130",
        "http://id.eaufrance.fr/GPR/127",
        "http://id.eaufrance.fr/GPR/203",
        "http://id.eaufrance.fr/GPR/73",
        "http://id.eaufrance.fr/GPR/132",
        "http://id.eaufrance.fr/GPR/129",
        "http://id.eaufrance.fr/GPR/211",
        "http://id.eaufrance.fr/GPR/168",
        "http://id.eaufrance.fr/GPR/50",
        "http://id.eaufrance.fr/GPR/216",
        "http://id.eaufrance.fr/GPR/31",
        "http://id.eaufrance.fr/GPR/167",
        "http://id.eaufrance.fr/GPR/128",
        "http://id.eaufrance.fr/GPR/192",
        "http://id.eaufrance.fr/GPR/96",
        "http://id.eaufrance.fr/GPR/131",
        "http://id.eaufrance.fr/GPR/200",
        "http://id.eaufrance.fr/GPR/209",
        "http://id.eaufrance.fr/GPR/134",
        "http://id.eaufrance.fr/GPR/190",
        "http://id.eaufrance.fr/GPR/122",
        "http://id.eaufrance.fr/GPR/133",
        "http://id.eaufrance.fr/GPR/137",
        "http://id.eaufrance.fr/GPR/121"
    ]
},