# Kaggle_PHEMS_Hackathon -- Early Sepsis Prediction





## Competition Info
[Competition Link](https://www.kaggle.com/competitions/phems-hackathon-early-sepsis-prediction/overview)

## Background on Sepsis
Sepsis is a life-threatening condition that occurs when the body’s response to an infection leads to tissue damage, organ failure, or death. In Europe, pediatric sepsis is a major concern, particularly in pediatric intensive care units (PICUs), where infection is one of the leading causes of morbidity and mortality in children. Early detection and timely administration of antibiotics are essential for improving outcomes in pediatric sepsis, as delays in treatment increase mortality rates. Each hour of delayed treatment has been associated with a 4-8% rise in mortality.

## Goal of the Competition
The primary objective is to develop a machine learning (ML) algorithm capable of early detection of sepsis in pediatric patients using retrospective physiological data.

## Files Provided

### Outcome Files
- **SepsisLabel_(train|test).csv**: Contains the outcome with the column `SepsisLabel` (1 for positive sepsis assessment, 0 for negative).

### Medical Data Files
- **devices.csv**: Tracks the usage of medical devices during patient PICU episodes. Each record represents a point in time when a specific device was used for a particular patient.
- **drugexposure.csv**: Contains records of drug administration to patients during their PICU episodes.
- **measurement_lab.csv**, **measurement_meds.csv**, **measurement_observation.csv**: Contain lab measurements and drug administration data during patient PICU episodes.
- **observation.csv**: Tracks observations recorded for patients during their PICU stay.
- **person_demographics_episode.csv**: Contains demographic information about patients.
- **proceduresoccurrences.csv**: Lists all procedures performed on a patient during an episode.


## Approaches:  (more detail in repositories )

 ### Decision_Tree 
 ### Ensemble_learning_LGBM 


# Ensemble_learning_LGBM 


### Train Data Columns
```python
columns_dict_train = {
    'drugsexposure': ['person_id', 'drug_datetime_hourly', 'drug_concept_id', 'route_concept_id'],
    'observation': ['person_id', 'observation_concept_name', 'valuefilled'],
    'devices': ['person_id', 'device_datetime_hourly', 'device'],
    'proceduresoccurrences': ['person_id', 'procedure_datetime_hourly', 'procedure'],
    'person_demographics_episode': ['person_id', 'age_in_months', 'gender'],
    'SepsisLabel': ['person_id', 'measurement_datetime', 'SepsisLabel']
}
```



### Train Hard Voting Model
```python
dt1, dt2, dt3 = hard_voting(d1_train, d2_train, d3_train, y)
```

## Functions
### `load_data_from_folder(folder_path)`
Loads CSV files from a given folder into a dictionary of DataFrames.

### `merge_grouped_datasets(d1, d2, d3, d4, d5, d6)`
Merges multiple datasets grouped by `person_id`.

### `extract_datetime_features(df, column)`
Extracts year, month, day, hour, and weekday from datetime columns.

### `preprocess_data(df, datetime_col, preprocessor=None, is_train=True)`
Preprocesses data by handling missing values, encoding categorical features, and standardizing numerical features.

### `hard_voting(data1, data2, data3, y)`
Trains three LightGBM classifiers and aggregates their predictions using hard voting.

## Training and Prediction
1. Load training and test data.
2. Preprocess features.
3. Train the hard voting model.
4. Apply the trained model to test data.
5. Generate predictions.










 
 

