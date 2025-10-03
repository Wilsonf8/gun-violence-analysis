# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a data analysis project focused on gun violence data in the United States. The primary dataset is `gun_violence_cleaned.csv`, a large (~158 MB) CSV file containing detailed incident records from 2013 onwards.

## Dataset Structure

The `gun_violence_cleaned.csv` file contains comprehensive gun violence incident data with the following key fields:

- **Incident identifiers**: `incident_id`, `date`, `incident_url`
- **Location data**: `state`, `city_or_county`, `address`, `latitude`, `longitude`, `congressional_district`, `state_house_district`, `state_senate_district`
- **Casualty counts**: `n_killed`, `n_injured`, `num_victims`, `num_suspects`
- **Demographic breakdowns**:
  - `num_males`, `num_females`, `num_adults`, `num_teens`
  - `num_adult_suspects`, `num_adult_victims`, `num_teen_suspects`, `num_teen_victims`
  - `num_male_suspects`, `num_male_victims`, `num_female_suspects`, `num_female_victims`
- **Incident details**: `incident_characteristics`, `gun_type`, `gun_stolen`, `n_guns_involved`
- **Participant data**: `participant_age`, `participant_age_group`, `participant_gender`, `participant_name`, `participant_relationship`, `participant_status`, `participant_type`
- **Additional context**: `location_description`, `notes`, `sources`

## Data Characteristics

- **Size**: The CSV is approximately 158 MB, requiring efficient data loading strategies
- **Temporal coverage**: Data starts from 2013-01-01
- **Incident types**: Include mass shootings, officer-involved incidents, domestic violence, gang involvement, drive-by shootings, home invasions, suicides, murder/suicides, and more
- **Participant fields**: Use delimiter `||` for multiple participants and `::` to separate participant index from values

## Development Environment

- **Python version**: 3.10.6
- **Jupyter**: Available with full stack (Lab 4.2.5, Notebook 7.2.2)
- **Working directory**: `/Users/wilsonflores/Fall 2025/Data Analysis/Project 2`

## Working with the Data

When analyzing this dataset:

1. **Memory considerations**: The CSV is large; consider using `pandas.read_csv()` with `chunksize` parameter or filtering columns with `usecols` if memory becomes an issue
2. **Participant data parsing**: Multiple participants are stored in pipe-delimited format (`||`) with indexed values using `::` separator
3. **Geographic analysis**: Multiple geographic levels available (congressional, state house, state senate districts)
4. **Characteristic flags**: The `incident_characteristics` field contains multiple tags separated by `||`

## Commands

- **Start Jupyter Lab**: `jupyter lab`
- **Start Jupyter Notebook**: `jupyter notebook`
- **Run Python script**: `python3 <script_name>.py`

## Analysis Workflow

The `exploring.ipynb` notebook is the primary analysis file for exploratory data analysis on the gun violence dataset.
