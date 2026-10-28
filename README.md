# Crysalis: context-guided geometry construction

This repository provides the code, frozen models, computational inputs, partitions and numerical source data accompanying the Crystal Growth & Design manuscript on context-guided geometry selection under a fixed crystal-assembly policy.

Download both archives from the [versioned release](https://github.com/Leoluis0705/Crysalis-CGD-Reproducibility/releases/tag/cgd-recovery-20261028).

- **Crysalis_CGD_Reproducibility_20261028.zip**: original implementation, four frozen model checkpoints, parent records, policy split, four-fold assignments, training inputs, seeds, portable commands and verification outputs.
- **Crysalis_CGD_Source_Data_20261028.zip**: recorded figure-level data, trajectories, and DFT input geometries/settings. Licensed pseudopotential contents are excluded.

The reproducibility ZIP contains README.md and run.py. The first check is `python run.py verify` with the documented environment.

## Verification scope

Both scorer training pipelines were rerun from stored features and force labels. Selected force values and NDCG@5 agree with all 663 development events. Frozen inference reproduces the selected candidates in all 429 additional-parent events. Two K=24 assembly trajectories reproduce their recorded actions and candidate identities. The 34 included original tests pass. Full policy/decoder training and all physical evaluations were not rerun for this release.

The 512 generation conditions exclude both scorer-development cohorts. Of these parents, 464 were used for fixed-policy training and 48 for policy validation. This is a fixed-policy geometry-selection comparison, not a whole-generator test on parents unseen by every component.

Historical model files are preserved; new scorer retraining outputs are separate. The release manifest records SHA-256 values. No claim of bitwise reproduction across arbitrary hardware is made.
