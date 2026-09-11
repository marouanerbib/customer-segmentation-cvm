# Segmentation Client CVM — Opérateur Télécom

Segmentation K-Means de 8000 clients prépayés en 8 segments, à partir de leurs usages (recharge, appels, VAS, data, international), avec un plan d'activation marketing par segment.

## Démarche

1. **Exploration des données** — statistiques descriptives, distributions, matrice de corrélation
2. **Preprocessing** — standardisation (StandardScaler)
3. **Segmentation** — K-Means (K=8), score de silhouette 0.22, profiling des clusters
4. **Visualisation** — Snake Plot des profils par segment
5. **Plan d'activation** — nom et action marketing par segment

## Dataset

`base_seg_gsm.csv` — 8000 clients prépayés anonymisés d'un opérateur télécom :

| Variable | Description |
|---|---|
| `ID` | Identifiant unique du client |
| `MMPR` | Montant Moyen Par Recharge (proxy de l'ARPU) |
| `FREQR` | Fréquence de Recharge |
| `POIDS_VAS` | Part des Services à Valeur Ajoutée |
| `POIDS_IN` | Part des appels entrants |
| `POIDS_IN_OFFN` | Part des appels entrants depuis la concurrence |
| `POIDS_OPK` | Part des communications Off-Peak |
| `POIDS_ONG` | Part des communications Off-Net sortantes |
| `POIDS_INT` | Part des communications internationales |
| `POIDS_ONN` | Part des communications On-Net |
| `SMART_PHONE` | Client équipé d'un smartphone (0/1) |
| `MULTI_EQUIPE` | Client possédant plusieurs SIM (0/1) |
| `USERS_INTERNET` | Client utilisant la Data (0/1) |

## Segments et plan d'activation

| Segment | Caractéristiques | Action marketing |
|---|---|---|
| Elite Connectée | ARPU élevé, 99% smartphone, usage mixte | Programme VIP, ligne prioritaire 24/7 |
| Receveurs Économes | Faible budget, essentiellement récepteurs, 0% data | Fidélisation par appel + 1 Go offert 3 mois |
| Fugueurs Off-Net | 83% des appels vers la concurrence | Forfait d'appel illimité + plage horaire gratuite 20h-22h |
| Accros aux Services (VAS) | Fort usage des services à valeur ajoutée | -50% sur abonnement VAS |
| La Majorité Silencieuse | Profil moyen, usage voix standard | Bonus recharge +50% |
| Opportunistes Multi-SIM | 68% multi-équipés | Forfait Data Champion — 20 Go à 50 DH/mois |
| Globe-Trotters | 74% de communications internationales | Package international illimité vers 10 destinations |
| 100% Digital | 100% utilisateurs data | Accès prioritaire 5G + 20 Go bonus mensuels |

## Setup

```bash
python -m venv venv
source venv/bin/activate  # Windows : venv\Scripts\activate
pip install -r requirements.txt
```

`pandas` · `numpy` · `matplotlib` / `seaborn` · `scikit-learn`

## Structure

```
├── base_seg_gsm.csv                # Dataset source
├── cvm.ipynb                       # Notebook d'analyse
├── resultats_segmentation_cvm.csv  # Résultats de la segmentation
├── requirements.txt
└── README.md
```

## Auteurs

Falleiz Belemcoabga · Marouane Rbib · Vincent Mendy
