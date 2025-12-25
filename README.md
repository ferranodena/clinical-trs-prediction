# 🧠 Predicció de la Resistència al Tractament en l'Esquizofrènia (TRS)

Aquest repositori conté el projecte desenvolupat per al laboratori de l'assignatura **Introducció a l'Aprenetatge Automàtic (IAA)** de la **UPC** (Curs 2025/26). L'objectiu és construir un model predictiu capaç d'identificar pacients amb esquizofrènia que presenten resistència al tractament antipsicòtic estàndard (Treatment-Resistant Schizophrenia, TRS).

## 📋 Resum del Projecte

La identificació precoç del TRS és un repte clínic fonamental. Aquest projecte utilitza un conjunt de dades multimodals (clíniques, genètiques i de neuroimatge) de 9.000 pacients per donar suport a la decisió mèdica mitjançant aprenentatge automàtic.

### Models Implementats

- **SVM (Support Vector Machine)**: Amb preprocessament de normalització i PCA.
- **XGBoost**: Optimitzat per gestionar el desbalanceig de dades.
- **Regressió Logística Custom**: Implementació des de zero amb descens de gradient per mini-batches.
- **EBM (Explainable Boosting Machine)**: Model final seleccionat per la seva transparència i alt recall.

## 🚀 Model Final Seleccionat: EBM

S'ha escollit el model **Explainable Boosting Machine (EBM)** com a solució òptima degut a la seva natura de "caixa de vidre", que permet interpretar cada predicció en un entorn clínic real.

### Rendiment (Test Set)

- **Accuracy**: 0.59
- **Recall (TRS)**: 0.59 (Prioritzat per minimitzar falsos negatius clínics)
- **Precision (TRS)**: 0.40
- **F1-Score**: 0.47
