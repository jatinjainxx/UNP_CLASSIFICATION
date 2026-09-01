# UNP_CLASSIFICATION

I, along with my teammates, did this project in collaboration with UNP, with the objective of supporting PCOS diagnosis using clinical and self-reported patient data, framed around a health-economics lens rather than accuracy alone. PCOS is often under- or inconsistently diagnosed because its symptoms overlap with other hormonal disorders, so the project's goal was to build models that could genuinely support that diagnostic process, not just classify a dataset well.

The dataset covers 541 patients across 44 clinical and lifestyle features — hormone levels, follicle counts, BMI, and self-reported symptoms like weight gain and skin darkening. Working in Python, I built a full pre-processing pipeline that corrected a data-leakage bug common in published work on this dataset (applying class-balancing before the train/test split, which inflates reported accuracy), and used SMOTENC instead of standard SMOTE to correctly handle the dataset's mix of numeric and categorical features.

The core of the project is a two-tier modelling approach: a full clinical model using all available features, and a self-reportable screening model using only symptoms a patient could report without a clinical exam. I trained and tuned Logistic Regression, Random Forest, and Decision Tree classifiers, selected the best model per tier using cross-validated recall (prioritizing catching true PCOS cases over raw accuracy, given the clinical cost of a missed diagnosis), and validated the comparison statistically using McNemar's test. I also examined feature importance and odds ratios to keep the models interpretable, not just predictive.

The key finding is a quantified trade-off: the full clinical model catches about 97% of PCOS cases, while the screening model — using only self-reportable symptoms — catches about 86%, a measurable cost of screening without a clinical exam. That gap is the project's central contribution: it puts a number on what's gained and lost by relying on patient-reported symptoms alone, which is directly useful for thinking about low-cost, early screening tools in resource-constrained healthcare settings.


GOOGLE COLAB LINK: https://colab.research.google.com/drive/1dQQIacjXv6nBVe1UJI4W95snQ-VSJu5-?usp=drive_link

PPTX FILE LINK: https://docs.google.com/presentation/d/17XchvrFuqbglDbjyW74gTdmcbgNjxxng/edit?usp=drive_link&ouid=113795729665883596271&rtpof=true&sd=true
