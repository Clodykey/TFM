# Avaluació de dades sintètiques generades mitjançant Deep Learning per a la replicació de resultats d'assajos clínics en càncer colorectal

**Treball Final de Màster · MU Bioinformàtica i Bioestadística · UOC–UB · 2026**  
**Autora:** Claudia Pascual Tomàs  
**Directors:** Alfonso Esteban Lasso · Javier Martínez · Jordi Cortés Martínez

---

## Descripció

Aquest repositori conté els scripts d'anàlisi estadística del TFM, implementats en R Markdown. L'objectiu del treball és avaluar si les dades sintètiques generades per un algorisme TVAE (*Tabular Variational Autoencoder*), desenvolupat per Alfonso Esteban Lasso (INARI BIOTECH S.L.), poden replicar els resultats publicats de dos assajos clínics de fase III en càncer de colon adjuvant.

La validació segueix un marc progressiu de quatre nivells: divergència de Kullback-Leibler normalitzada (univariant), proves chi-quadrat de Pearson (bivariant), models de Cox amb solapament d'intervals de confiança (multivariant) i gràfics de Bland-Altman (concordança). S'inclou també un test d'indistingibilitat.

---

## Assajos clínics analitzats

| Identificador | Nom | Disseny | N |
|---|---|---|---|
| NCT00079274 | N0147 | FOLFOX vs. FOLFOX + Cetuximab en estadi III | ~2.686 |
| NCT01150045 | CALGB/SWOG 80702 | Celecoxib vs. placebo afegit a FOLFOX (2×2 factorial) | ~2.527 |

Les dades originals provenen de **Project Data Sphere** (PDS) i del **NCTN Data Archive**. Les dades sintètiques van ser generades per INARI BIOTECH S.L. i no es distribueixen en aquest repositori.

---

## Estructura del repositori

- `NCT00079274.Rmd` — Anàlisi complet de l'assaig N0147
- `NCT01150045.Rmd` — Anàlisi complet de l'assaig CALGB/SWOG 80702
- `NCT00079274_unido.csv` — Dataset combinat real+sintètic (N0147) — no inclòs públicament
- `NCT01150045_unido.csv` — Dataset combinat real+sintètic (CALGB) — no inclòs públicament
- `README.md`

---

## Anàlisis incloses

Cada script `.Rmd` implementa:

- Taules de característiques basals (`gtsummary`)
- Divergència KL normalitzada per entropia de Shannon (univariant)
- Proves chi-quadrat d'independència per parells de variables (bivariant)
- Corbes de Kaplan-Meier (OS i DFS) amb `survminer`
- Models de Cox multivariants amb forest plots (`forestploter`)
- Forest plots de subgrups
- Gràfics de Bland-Altman de concordança de hazard ratios
- Gràfics d'àrea acumulada d'abandonament del tractament

---

## Requisits

R ≥ 4.2 amb els paquets: `survival`, `survminer`, `forestploter`, `gt`, `gtsummary`, `ggplot2`, `tidyr`, `dplyr`, `flextable`, `blandr`, `philentropy`, `extrafont`, `gridExtra`, `purrr`

---

## Nota sobre les dades

Les dades originals de Project Data Sphere estan subjectes als termes d'ús de la plataforma i no es poden redistribuir. Les dades sintètiques són propietat d'INARI BIOTECH S.L. Per tant, **els fitxers CSV no s'inclouen en aquest repositori públic.** Els scripts estan documentats per a reproduir l'anàlisi amb accés propi als datasets.

---

## Citació

Si fas servir o fas referència a aquest codi, si us plau cita:

> Pascual Tomàs, C. (2026). *Avaluació de dades sintètiques generades mitjançant Deep Learning per a la replicació de resultats d'assajos clínics en càncer colorectal*. TFM, MU Bioinformàtica i Bioestadística, UOC–UB.
