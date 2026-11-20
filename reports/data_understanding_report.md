## Findings Summary — Data Understanding

### 1. Dataset Overview

The dataset contains approximately 615,402 food business records from the UK Food Hygiene Rating Scheme (FHRS) and Food Hygiene Information Scheme (FHIS). It includes information about food businesses, their locations, inspection outcomes, hygiene-related scores, and rating dates.

The dataset contains two distinct inspection schemes:
- **FHRS:** 556,344 records.
- **FHIS:** 59,058 records.

These schemes use different rating systems and must be considered separately during analysis.

### 2. Dataset Structure

The dataset contains a mixture of numerical, categorical, date-related, geographical, and text-based attributes.

Important groups of variables include:
- Business information: `BusinessName`, `BusinessType`, `BusinessTypeID`.
- Geographical information: `LocalAuthorityName`, `PostCode`, `Latitude`, `Longitude`.
- Inspection information: `RatingValue`, `RatingDate`, `SchemeType`.
- Inspection scores: `Hygiene`, `Structural`, `ConfidenceInManagement`.

### 3. Key Findings

- The `RatingValue` column contains both numerical-looking rating values and non-numerical outcomes or statuses. These values cannot all be interpreted as a single numerical scale.
- FHRS and FHIS represent different rating systems. Their outcomes should be analysed separately rather than combined into one numerical rating.
- Geographical coordinates are missing for a substantial proportion of records. This may limit geographical analysis and mapping.
- `RatingDate` contains missing values. The distribution of missing dates should be investigated across inspection schemes and rating outcomes before deciding how to handle them.
- `RightToReply` contains relatively few populated records and requires further consideration as a text-based field.
- Duplicate checks on the selected business identifier and complete records did not identify exact duplicates in the initial investigation. However, the appropriate business identifier and its uniqueness should be verified before relying on it for record-level analysis.

### 4. Data Quality Considerations

The initial investigation identified potential issues involving completeness, consistency, validity, and the interpretation of certain variables.

In particular:
- Missing geographical coordinates may affect mapping coverage.
- Missing rating dates may affect time-based analysis.
- Different rating schemes require separate treatment.
- Some categorical fields contain statuses that should not be interpreted as inspection scores.
- Free-text fields may require additional processing if they are included in later analysis.

These observations identify areas requiring further assessment. They do not, by themselves, establish that the underlying records are inaccurate.

### 5. Implications for Future Analysis

Before performing exploratory analysis, the dataset requires a structured data quality assessment and a documented cleaning strategy.

Future analysis should:
- Separate FHRS and FHIS where their rating systems are not directly comparable.
- Investigate missing values and their relationship with other variables.
- Validate geographical coordinates and date fields.
- Establish appropriate identifiers for businesses and records.
- Define which variables are suitable for each analytical question.

The objective is to establish a reliable analytical dataset while preserving the original source data and documenting all transformations.