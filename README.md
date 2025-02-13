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



