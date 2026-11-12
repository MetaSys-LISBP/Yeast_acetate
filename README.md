# Yeast_acetate: models and data for acetate exchange in yeast

This repository contains the COPASI models and experimental concentration time courses used to quantify acetate and ethanol fluxes in *Saccharomyces cerevisiae* in the manuscript:

**Bidirectional acetate exchange couples ethanol turnover to acetyl-CoA metabolism in Saccharomyces cerevisiae**  
Anthony Carneiro, Mohammad Zishaan Kodooruth, Hanna Kulyk, Gilles Truan, Hélène Martin-Yken, Pierre Millard and Sara Castaño-Cerezo.

The study combines isotope tracing and metabolic flux analysis to resolve simultaneous acetate production and assimilation during sugar utilization. It examines how acetate exchange responds to changes in hexose uptake, fermentative and respiratory metabolism, deletion of *ALD6*, and expression of an acetate-to-mevalonate pathway. Tracing extracellular ethanol also reveals its contribution to acetate production during net ethanol overflow.

## Repository contents

The repository contains **51 COPASI files and 51 experimental data tables**, covering 17 combinations of experimental condition and growth phase, each with three biological replicates.

| File or directory | Contents |
| --- | --- |
| [Figure 1/](Figure%201/) | Wild-type cultures on glucose with 5 mM [U-¹³C]acetate. |
| [Figure 2/](Figure%202/) | Glucose-uptake perturbations with 2-deoxyglucose or MTH1-ΔT, and galactose/acetate cultures of wild-type, Δald6 and pathway-expressing strains. |
| [Figure 3/](Figure%203/) | [U-¹³C]ethanol-tracing experiments in wild-type and Δald6 strains, with separate fermentative and respiratory phases. |
| [description.xlsx](description.xlsx) | Experiment index linking file identifiers to biological replicates, medium composition, strain, growth phase and manuscript figures. |
| `*.cps` | COPASI files containing model equations, parameter values, fitting bounds, experimental-data mappings, weights and analysis settings. |
| `*.txt` | Tab-delimited concentration time courses used for parameter estimation. |
| [LICENSE](LICENSE) | GNU Affero General Public License, version 3. |

The directories group analyses by manuscript figure. Some datasets also support other main or supplementary figures. The tables below provide an overview, and `description.xlsx` gives the detailed figure-to-experiment mapping.

These files focus on metabolic flux estimation.

## Experimental conditions and file guide

All strains derive from *S. cerevisiae* CEN.PK2-1D. **WT** denotes wild type, **Δald6** denotes deletion of *ALD6*, **MTH1-ΔT** denotes the strain expressing the internally truncated MTH1 variant, and **2DG** denotes 2-deoxyglucose. The folder label `KO ALD6 + p114` identifies the Δald6 strain carrying **pI2M114**, which encodes the synthetic acetate-to-mevalonate pathway.

In the tables, `<r>` is the biological replicate number (`1`, `2` or `3`). File identifiers are shown for the `.txt` data tables. The corresponding `.cps` file is in the same directory.

Medium concentrations below describe the nominal culture supplementation. Each data table contains the measured concentrations over the fitted growth interval. All concentrations listed in the condition tables are in mM.

### Figure 1: acetate exchange during growth on glucose

| Directory | Data filename | Strain | Medium |
| --- | --- | --- | --- |
| `Figure 1/` | `g6.A.<r>.txt` | WT | 55 glucose + 5 [U-¹³C]acetate |

These experiments support Figure 1C–E and are also used in the flux comparisons in Figure 2 and Supplementary Figures 2–3.

### Figure 2: inhibition of glucose phosphorylation

Directories are relative to `Figure 2/Figure 2. 2DG/`. All cultures contain **55 mM glucose and 60 mM [U-¹³C]acetate**.

| Directory | Data filename | Strain | Added 2DG (mM) |
| --- | --- | --- | --- |
| `0mM 2DG/` | `g6.B.<r>.txt` | WT | 0 |
| `5mM 2DG/` | `g6.C.<r>.txt` | WT | 5 |
| `10mM 2DG/` | `g7.A.<r>.txt` | WT | 10 |
| `5mM ALD6 2DG/` | `g7.B.<r>.txt` | Δald6 | 5 |

The WT series supports Figure 2A–C; the Δald6 series is included in the supplementary flux comparisons.

### Figure 2: galactose/acetate cultures

Directories are relative to `Figure 2/Figure 2. Galactose acetate/`. All cultures contain **55 mM galactose and 60 mM [U-¹³C]acetate**.

| Directory | Data filename | Strain | Growth phase |
| --- | --- | --- | --- |
| `Fermentative/WildType/` | `g7.C.<r>.txt` | WT | Fermentative |
| `Respiratory/WildType/` | `g7.Crespi.<r>.txt` | WT | Respiratory |
| `Fermentative/KO ALD6/` | `g7.D.<r>.txt` | Δald6 | Fermentative |
| `Respiratory/KO ALD6/` | `g7.Drespi.<r>.txt` | Δald6 | Respiratory |
| `Fermentative/KO ALD6 + p114/` | `g7.E.<r>.txt` | Δald6 + pI2M114 | Fermentative |
| `Respiratory/KO ALD6 + p114/` | `g7.Erespi.<r>.txt` | Δald6 + pI2M114 | Respiratory |

The WT series supports Figure 2A–C,F. Comparisons of WT and Δald6 support Supplementary Figure 8, and comparisons of Δald6 with and without pI2M114 support Supplementary Figures 9–10 and the interpretation of the mevalonate experiments.

### Figure 2: reduced glucose uptake in the MTH1-ΔT strain

Directories are relative to `Figure 2/Figure 2. Mth1/`. Both phases are from cultures containing **55 mM glucose and 60 mM unlabeled acetate**.

| Directory | Data filename | Strain | Growth phase |
| --- | --- | --- | --- |
| `Phase 1/` | `g5.A.<r>.txt` | MTH1-ΔT | First phase |
| `Phase 2/` | `g5.A2.<r>.txt` | MTH1-ΔT | Second phase |

These experiments support the flux comparisons in Figure 2A–C and Supplementary Figures 2–3.

### Figure 3: ethanol tracing

Directories are relative to `Figure 3/`. All cultures contain **55 mM galactose, 60 mM unlabeled acetate and 10 mM [U-¹³C]ethanol**.

| Directory | Data filename | Strain | Growth phase |
| --- | --- | --- | --- |
| `A fermentative/` | `g8.A.<r>.txt` | WT | Fermentative |
| `A respi/` | `g8.Arespi.<r>.txt` | WT | Respiratory |
| `B fermentative/` | `g8.B.<r>.txt` | Δald6 | Fermentative |
| `B respi/` | `g8.Brespi.<r>.txt` | Δald6 | Respiratory |

The fermentative WT and Δald6 datasets support Figure 3A and 3B, respectively, and Supplementary Figure 7. Both growth phases are included in the supplementary flux comparisons.

## Data-table format

All `.txt` files have the same nine columns, separated by tabs, with a header in the first row.

| Column | Meaning | Unit |
| --- | --- | --- |
| `experiments` | Experiment identifier used in the data table; the filename identifies the biological replicate. | — |
| `time` | Elapsed time within the fitted growth interval. | h |
| `X` | Biomass concentration. | gDCW L⁻¹ |
| `Glc` | Extracellular hexose concentration: glucose or galactose, according to the condition. | mM |
| `EthC12` | Unlabeled extracellular ethanol. | mM |
| `AcC12` | Unlabeled extracellular acetate. | mM |
| `AcC13` | ¹³C-labeled extracellular acetate. | mM |
| `EthC13` | ¹³C-labeled extracellular ethanol. | mM |
| `Gly` | Extracellular glycerol. | mM |

**gDCW** means grams of dry cell weight. Biomass was calculated from optical density as `X = OD600 / 3.416`, as described in the manuscript.

## Model and flux definitions

The models describe central carbon metabolism and extracellular concentration dynamics, with unlabeled and labeled pools for isotope tracing. They distinguish acetate production through aldehyde dehydrogenase (Ald) from assimilation through acetyl-CoA synthetase (Acs), and represent forward and reverse alcohol dehydrogenase (Adh) fluxes separately. Ethanol evaporation is also represented.

Biomass-specific metabolic fluxes are assumed constant within each fitted growth phase, while biomass and extracellular concentrations vary over time. Each file defines 14 fitted parameters, including fluxes, growth rate and initial concentrations. Parameter estimation minimizes a weighted sum of squared residuals, with he column mappings, weights, parameter bounds and starting values stored in each file.

Key COPASI global quantities are:

| Quantity | Interpretation |
| --- | --- |
| `growth_rate` | Specific growth rate, in h⁻¹. |
| `v_glc_uptake` | Hexose uptake flux. |
| `v_ald_f` | Acetate formation through Ald. |
| `v_acs_f` | Acetate assimilation through Acs. |
| `v_adh_f` | Ethanol formation from acetaldehyde through Adh. |
| `v_adh_r` | Ethanol oxidation to acetaldehyde through Adh. |
| `v_pdc_f` | Pyruvate decarboxylase flux. |
| `v_Ace_net` | Net acetate flux: `v_ald_f - v_acs_f`. |
| `v_EtOH_net` | Net metabolic ethanol flux: `v_adh_f - v_adh_r`; evaporation is represented separately. |

Metabolic fluxes are expressed in **mmol gDCW⁻¹ h⁻¹**. Positive net exchange denotes production and negative net exchange denotes consumption. Opposing fluxes can therefore remain substantial even when net exchange is close to zero.

The experimental organism and condition are identified by this README, the directory and `description.xlsx`.

## Using the models

### Software

The files were saved with **COPASI 4.39 (build 272)**, the version used for the analyses described in the manuscript. COPASI installers and documentation are available from the [official COPASI website](https://copasi.org/). A spreadsheet viewer can be used to read `description.xlsx`; the data tables can be opened with a text editor or imported into other analysis software.

### Example: fit one biological replicate

1. Download the repository while preserving the directory structure, or clone it:

   ```bash
   git clone https://github.com/MetaSys-LISBP/Yeast_acetate.git
   cd Yeast_acetate
   ```

2. Open `Figure 1/g6.A.1.cps` in COPASI.
3. Open **Parameter Estimation**, then **Experimental Data**. Check that the experiment uses `g6.A.1.txt` from the same directory. If necessary, select this file manually. Retain the saved tab separator, header row, column mappings and weights.
4. Review the fitted parameters, bounds and **Particle Swarm** settings. The saved files specify an **iteration limit of 4,000**, a **swarm size of 50**, randomized starting values and a random-number seed of `0`.
5. Run **Parameter Estimation** and inspect the **Result** view to compare fitted concentration profiles with the experimental data and review the estimated parameters and fit statistics.
6. To save numerical results, assign an output filename through the task's **Report** settings. Save any modified file under a new name to retain the supplied settings.
7. Repeat with replicates 2 and 3 and the other conditions of interest. Each file fits one biological replicate independently.

Particle swarm optimization is stochastic, and a seed of `0` requests an automatically selected seed. Repeated fits may therefore return different parameter values. The saved files retain the analysis configuration; numerical agreement should be assessed together with fit quality.

See the guides to [experimental-data configuration](https://copasi.org/Support/User_Manual/Tasks/Parameter_Estimation/Experimental_Data/), [parameter-estimation results](https://copasi.org/Support/User_Manual/Tasks/Parameter_Estimation/Result/) and [particle swarm options](https://copasi.org/Support/User_Manual/Methods/Optimization_Methods/Particle_Swarm/) for further details.

## Citation and contact

Please cite the associated manuscript listed above when using these models or data. The manuscript provides the experimental procedures, biological interpretation and supplementary analyses.

For questions, contact the corresponding authors:

- Pierre Millard: [millard@insa-toulouse.fr](mailto:millard@insa-toulouse.fr)
- Sara Castaño-Cerezo: [castanoc@insa-toulouse.fr](mailto:castanoc@insa-toulouse.fr)

## License

This repository is distributed under the **GNU Affero General Public License, version 3**. See [LICENSE](LICENSE) for the full terms.
