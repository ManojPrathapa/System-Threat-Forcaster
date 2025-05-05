# 🛡️ Malware Detection Challenge

This repository contains my solution for a machine learning competition focused on predicting malware infections based on telemetry data from antivirus software.

## 📌 Problem Statement

The objective of this competition is to predict the likelihood of a machine being infected by various malware families. The dataset includes telemetry data collected by antivirus software, and each entry corresponds to a unique machine.

Using this data, we aim to build a binary classification model that can accurately identify machines that are infected (label `1`) versus those that are not (label `0`).

## 📁 Dataset

The dataset provided includes the following files:

- **`train.csv`** — Training data with features and the target malware infection label.
- **`test.csv`** — Test data for which predictions need to be made.
- **`sample_submission.csv`** — A sample format for submission.

### Columns (Partial List)

- `MachineID`: Unique identifier for each system
- `ProductName`, `EngineVersion`, `AppVersion`, `SignatureVersion`: Antivirus product and update metadata
- `IsBetaUser`, `IsPassiveModeEnabled`, `RealTimeProtectionState`: User and protection configuration
- `CountryID`, `CityID`, `GeoRegionID`: Geographic indicators
- `OSVersion`, `OSBuildNumber`, `OSInstallType`, etc.: System OS information
- `Processor`, `PrimaryDiskType`, `TotalPhysicalRAMMB`: Hardware specifications
- `IsSecureBootEnabled`, `IsVirtualDevice`, `IsGamer`: Miscellaneous system attributes
- `DateAS`, `DateOS`: Date metadata
- `target`: Binary label (0: Not infected, 1: Infected)

The full dataset contains **153 columns** and covers a wide range of system properties.

## 🎯 Evaluation Metric

The submissions are evaluated using **accuracy score**, which compares the predicted labels against the ground truth.

```python
from sklearn.metrics import accuracy_score
accuracy_score(y_true, y_pred)
