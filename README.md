Behavioral Data and ROI-Level fMRI Analysis Outputs from a Naturalistic Emotional Film-Viewing Study
1. Overview
This repository accompanies a naturalistic emotional film-viewing fMRI
study examining goal-related appraisal and responsibility attribution
during film viewing.

The deposited materials include behavioral rating files, derived
behavioral time series, ROI-level first-level fMRI model estimates,
design matrices, downstream ROI-level statistical and Bayesian analysis
outputs, and Python analysis scripts.

Raw fMRI images, full BOLD time series, motion-confound files, and the
film/audio stimulus are not included in this repository. The ROI-level
beta tables and statistical outputs are derived analysis products rather
than raw neuroimaging data.
2. Repository files
The Zenodo record contains the following archives and this README:
- code.zip: Python scripts used for behavioral and fMRI-related
  analyses.
- data.zip: behavioral data and derived analysis outputs.
- README.md: documentation for the deposited files.
3. Contents of data.zip
The files are stored under the top-level directory data/ in the
supplied archive.
3.1 Behavioral data
- data/raw/goal/: 23 CSV time-series files containing time and
  goal columns.
- data/raw/angecy/: 23 CSV time-series files containing time and
  zrgy columns. The folder name is preserved as it appears in the
  supplied archive; these files represent the responsibility/agency
  appraisal time series.
- data/raw/emo/: 47 CSV files containing emotion ratings. The files
  include time and frame information and emotion-rating columns
  labelled in Chinese.
The participant/file identifiers are study codes. No names or contact
details are intentionally included in these files. Before public
release, the depositor should verify that the codes and any combinations
of variables cannot be linked to identifiable individuals.
3.2 Derived behavioral data
data/derived/behavioral/ contains aggregated or transformed behavioral
time series, input-file inventories, model coefficient tables, and an
Excel workbook with results from the behavioral models. Files include:
- per_second_data_original_aggregated.csv
- w3.csv
- w3fmri.csv
- table1_two_predictors_coefficients.csv
- table2_four_predictors_coefficients.csv
- two_models_original_data_results.xlsx
- input_files_goal.csv
- input_files_responsibility.csv
The precise interpretation of each variable and any transformation or
scaling should be taken from the study protocol and analysis scripts.
The deposited files retain their original variable names; some emotion
variable names are in Chinese.
3.3 ROI-level fMRI model outputs and design matrices
data/derived/group_level_221/ contains six ROI-level beta tables and
two design matrices:
- beta_layer1_goal_resp_goal.csv
- beta_layer1_goal_resp_responsibility.csv
- beta_goal_facil.csv
- beta_goal_block.csv
- beta_self_resp.csv
- beta_other_resp.csv
- design_goal_direction.csv
- design_responsibility_direction.csv
The beta tables contain participant-level estimates for 221 ROI entries,
with participant codes in the first column. The design matrices document
the regressors used in the directional models. These files are analysis
outputs; they are not raw voxelwise fMRI images.
3.4 Bayesian analysis outputs
data/derived/bayesian/ contains ROI-level Bayes-factor results,
classification tables, summary counts, and the selected ROI list. Some
outputs use the neural215 subset defined by the corresponding analysis
scripts.
4. Contents of code.zip
The archive contains the following six Python scripts:
1. 01_two_models_behaviour.py
   Fits behavioral binomial generalized linear models using two bipolar
   predictors and a four-predictor directional model. The script
   includes a heteroskedasticity and autocorrelation consistent (HAC)
   covariance approach.
2. 02_glm_joint_goal_agency.py.py
   Specifies the first-level ROI GLM that jointly models goal and
   responsibility/agency appraisal.
3. 03_glm_directional_goal_agency.py.py
   Specifies directional first-level ROI GLMs for goal facilitation
   versus obstruction and self versus other responsibility attribution,
   while controlling for the other appraisal dimension.
4. 04_group_level_roi_statistics.py.py
   Performs ROI-level group statistics and related result/figure
   generation.
5. 05_bf_shared_distinct.py.py
   Performs Bayesian evidence classification for shared and
   dimension-specific neural correlates of goal and responsibility
   appraisal.
6. 06_bf_directional.py.py
   Performs Bayesian evidence classification for directional goal and
   responsibility effects.
The script filenames above are reproduced exactly as they appear in the
supplied archive.
5. Reproducibility and software requirements
The scripts use Python and packages including NumPy, pandas,
statsmodels, SciPy, Matplotlib, Nilearn, NiBabel, and Pingouin. Exact
package versions are not pinned in the supplied scripts; users seeking
to rerun the analyses should establish and document a compatible
environment.

The archives do not contain all inputs required to rerun every script
from the beginning. In particular, the first-level fMRI scripts expect
ROI BOLD time-series files and motion-confound files that are not
included in this deposit. Several scripts also contain machine-specific
local paths that must be updatad before execution. Some behavioral
scripts likewise expect input directories that may need to be mapped to
the deposited folder structure.

Accordingly, the deposited beta tables, design matrices, and statistical
outputs are provided as derived analysis products. The repository
supports inspection of these outputs and selected downstream analyses,
but it does not provide a complete end-to-end reconstruction from raw
fMRI data.
6.Ethics, Consent, and Data Sharing

All participants provided written informed consent in person. The consent permitted public sharing of research data.

The deposited data are intended for research reuse and should be handled in accordance with the applicable consent conditions, privacy requirements, and institutional policies. Direct personal identifiers are not intentionally included in the repository.

Dataset DOI

https://doi.org/10.5281/zenodo.23686415
7. Film stimulus and copyright
The film stimulus used in the study is not included in this repository
because permission to redistribute the film or its audio has not been
obtained. This repository does not grant any rights to the film, its
soundtrack, or other copyrighted stimulus materials. Users must obtain
the relevant permissions before accessing or redistributing such
materials.
8. Data availability and reuse
The behavioral data and research data products in this repository are
made available for research reuse in accordance with the consent
conditions and the license selected for this Zenodo record. The license
for the deposited files does not extend to the film or other third-party
copyrighted materials.

Please cite the associated manuscript and the Zenodo record DOI when
using these data or analysis outputs.
