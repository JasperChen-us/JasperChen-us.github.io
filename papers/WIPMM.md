---
layout: default
title: Where Is a Prediction Model Miscalibrated, and for Whom? Local Audits in Outcome-Learned Pockets
permalink: /papers/WIPMM/
---

# Where Is a Prediction Model Miscalibrated, and for Whom? Local Audits in Outcome-Learned Pockets

**Status:** Accepted at *AICCC*; [Poster](https://www.dropbox.com/scl/fi/obx7zedkawybq252pzzfm/Cluster-bias-detection_SCI_2025.pdf?rlkey=yec4854wggbooubus6r1501u7&st=ksi4wpxk&dl=0) at *Society for Causal Inference*
**arXiv:** [arXiv link here](https://arxiv.org/abs/2611.02639)

## Abstract
A prediction model can be accurate on average while systematically overpredicting for some patients and underpredicting for others. We introduce a local calibration audit that identifies where these errors occur and whether they differ between demographic groups. Using random-forest similarity and ridge regression, the audit learns groups of observations (“pockets”) from features and outcomes in one sample, then estimates prediction errors and between-group gaps in a separate sample. In simulations, the combined audit outperformed the strongest alternative grouping in 15 of 17 scenarios with a planted group gap and in 12 of 15 scenarios with a smaller, region-wide error. Error rates exceeded the 5% target for local mean errors in one clustered design. In synthetic care-management data, a cost-based score mapped to chronic illness showed no detectable overall error, yet it underpredicted illness in the sickest pocket and overpredicted it in all four healthier pockets.

