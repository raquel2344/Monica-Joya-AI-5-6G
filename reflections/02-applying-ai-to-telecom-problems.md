# Reflection 2: Applying AI, the Glitches I Overcame, and Where I Grew

The second half of the course applied machine learning to network problems. The work that taught me the most was usually the debugging, so this essay is organized around what I built, the specific problems I hit, and the skills that came out of it.

## Models I built

In Module 03 I built my first model, a Random Forest regressor that predicts hourly network traffic. The accuracy came from feature engineering rather than the model: I added lag features and rolling averages, and feature importance confirmed that the values from one hour and twenty-four hours earlier carried the most signal. The Module 03 exercises added an Isolation Forest and DBSCAN for anomaly detection, scored with precision, recall, and F1 rather than accuracy because the anomalies are rare, and K-means with PCA for customer segmentation. In Module 04 I modeled 5G resource allocation, weighting three slices by priority and normalizing the weighted demand to a fixed 500-unit pool, which produced a split of URLLC 139, eMBB 278, and mMTC 82. Module 06 compared three forecasting families, ARIMA, Linear Regression, and an LSTM, on a year of hourly data, and the Module 10 midterm combined SimPy, Mesa, and scikit-learn into one study of a network.

## Glitches I overcame

Most modules came with starter code that was broken or written for an older library version, and fixing those was where the real learning happened.

- **Target leakage (Module 06).** The Linear Regression model scored almost perfectly. The cause was that its moving-average features (ma_3, ma_24, ma_168) included the current hour, so each feature already contained the value being predicted. I kept the starter code, changed only the one line the current pandas version needed (freq='H' to freq='h'), and documented the leakage instead of reporting the misleading score.
- **A demand loop bug (Module 04).** The starter code recorded one demand value per slice instead of one per connection, because the append sat outside the inner loop. I moved it inside so demand was summed correctly before allocation.
- **Broken knowledge distillation (Module 07).** The distillation section defined a student model, a teacher, and a loss, but never connected them, so the student trained on its own. I wired the student to train against the teacher's softened predictions and corrected the temperature so it was applied the standard way. I also hit TensorFlow install problems that broke the notebook tools, and I learned to test the compression step on a tiny model before a full run to catch failures early.
- **A removed Mesa API (Module 10).** The agent-based model used mesa.time.RandomActivation, which was removed in Mesa 3, so I migrated it to the current approach where the model steps its agents directly. The starter also only printed a message when a router was overloaded without moving any load, so I connected that step so a congested router offloads to neighbors, which is what produced the recovery in the results.

## Skills I improved

The technical skills that improved most are practical machine learning (model selection, feature engineering, and choosing the right metric), debugging and updating unfamiliar code across library versions, and evaluating results honestly, since catching the target leakage taught me to treat a near-perfect score as something to investigate. I also practiced writing up each result in plain, exact language.

## Areas for future growth

I want to take the edge computing work from Module 07 further and deploy a compressed model on real hardware rather than in simulation. I also want to work with real network and sensor data instead of synthetic datasets, where the patterns are messier and the failures are more informative. Both point toward the data and modeling work in digital energy, which is the direction I am building toward.
