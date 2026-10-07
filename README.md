# Mask Architecture Anomaly Segmentation for Road Scenes

Course project for *Machine Learning for Mathematical Engineering* (MSc Mathematical Engineering, Politecnico di Torino, 2026).
Team: Sonia Bressan, Arianna Brocco, Alessia Gambuzza, Maria Verdari. Original repository: [MariaVerdari/AnomalySegmentation2026](https://github.com/MariaVerdari/AnomalySegmentation2026).

**Goal.** Segmentation models for autonomous driving are over-confident on objects they have never seen. We detect these out-of-distribution (OoD) obstacles pixel by pixel.

**What we did**
- Compared post-hoc anomaly scores (MSP, MaxLogit, entropy, temperature scaling, RbA) on a pixel-based model (ERFNet) and a mask-based model (EoMT), on five benchmarks: RoadAnomaly21, RoadObstacle21, RoadAnomaly, Fishyscapes Static, Lost&Found.
- Proposed a prototype-based extension of EoMT: class prototypes are computed from the object queries, and anomaly scores come from cosine and Mahalanobis distances (shared or per-class covariance), with fine-tuning of a cosine classifier.
- Metrics: AuPRC and FPR95.

**Result.** EoMT outperforms ERFNet on all five datasets; among the prototype-based variants, the second fine-tuning gives the best AuPRC on RoadObstacle21 (86.0) and RoadAnomaly (32.8).

**Report:** [report.pdf](report.pdf)

The code is based on the ERFNet and EoMT code bases provided for the course; see the folders `eval/` and `eomt/`.
