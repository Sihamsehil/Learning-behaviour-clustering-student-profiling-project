# Dataset 2 Behavioral Lifestyle

Behavioral and lifestyle dataset. It uses survey-style features about study habits, sleep, stress, motivation, social media, focus, planning, and wellbeing. Grade columns were not the focus here.

## Files included
- `dataset2_behavioral_lifestyle_dataset.xlsx`: The master Excel workbook containing the raw or compiled data across multiple sheets.
- `dataset2_behavioral_lifestyle_core.csv`: The core dataset containing primary survey responses and standard behavioral features before advanced processing.
- `dataset2_behavioral_lifestyle_ml_ready.csv`: Cleaned, encoded, and fully imputed version of the dataset optimized for machine learning models (e.g., categorical variables converted to numbers, no missing values).
- `dataset2_behavioral_lifestyle_extended.csv`: The complete dataset including all core features alongside advanced derived metrics, scores, and engineering features.
- `dataset2_behavioral_lifestyle_build_summary.csv`: A metadata summary file detailing pipeline execution, row counts, feature distributions, and generation metrics.
- `dataset2_behavioral_lifestyle_imputation_log.csv`: A detailed logging file tracking which missing values were filled, the methods used, and the changes made during data cleaning.

## Feature explanations

### Metadata & Provenance
* **`behavior_student_id`**: Anonymous generated student/sample identifier for behavioral dataset.
* **`source_dataset`**: Original file/source from which the row came.
* **`source_row_number`**: Original row number inside the source file.

### Demographics & Student Profiles
* **`age`**: Student age.
* **`gender_female_binary`**: Encoded gender indicator: 1 means female, 0 means male/other encoded from available answers.
* **`academic_level_num`**: Numeric study level/year when available.
* **`part_time_job_binary`**: 1 if the student has a part-time job, 0 otherwise.
* **`internet_quality_score`**: Internet quality score, usually scaled from 1 low to 5 high.

### Daily Time Allocation & Habits
* **`study_hours_daily`**: Estimated average daily study hours.
* **`self_study_hours_daily`**: Estimated daily self-study hours.
* **`online_classes_hours_daily`**: Estimated daily online class/online learning hours.
* **`social_media_hours_daily`**: Estimated daily non-academic social media time.
* **`gaming_hours_daily`**: Estimated daily gaming time.
* **`sleep_hours`**: Average sleep hours per night.
* **`screen_time_hours_daily`**: Estimated total daily screen time.
* **`exercise_minutes_daily`**: Estimated daily physical activity/exercise minutes.
* **`caffeine_intake_daily`**: Estimated daily caffeine intake count.

### Psychological & Academic Wellness
* **`mental_health_score`**: Mental health/self-reported wellbeing score when available.
* **`focus_score`**: Focus/attention score, usually 1 low to 5 high.
* **`burnout_score`**: Burnout level, usually 1 low to 5 high.
* **`productivity_score`**: Self-reported productivity score.
* **`stress_score`**: Stress level; higher means more stress.
* **`motivation_score`**: Motivation level.
* **`satisfaction_score`**: Satisfaction with school/major/program.

### Learning Organization & Engagement
* **`assignment_punctuality_score`**: How consistently assignments are submitted on time.
* **`attendance_engagement_score`**: Attendance/class engagement indicator.
* **`study_planning_score`**: How organized/planned the student’s study routine is.
* **`extra_academic_work_binary`**: 1 if the student does extra academic work beyond requirements.

### Derived Behavioral Metrics
* **`total_learning_hours_daily`**: Derived total learning time from study, self-study, and online learning.
* **`distraction_hours_daily`**: Derived daily distraction time from social media and gaming.
* **`sleep_balance_score`**: Derived score measuring how close sleep is to a healthy range.
* **`wellbeing_score`**: Derived wellbeing score combining mental health, stress, sleep balance, and burnout.
* **`discipline_score`**: Derived discipline score from punctuality, planning, attendance, and focus.
* **`engagement_score`**: Derived engagement score from learning hours, exercise, motivation, and extra academic work.

### Behavioral Risk & Integrity Trackers
* **`distraction_risk_score`**: Derived risk score from high screen time, social media, and gaming.
* **`behavioral_risk_score`**: Overall derived behavioral risk indicator.
* **`observed_behavior_feature_count`**: Number of real observed behavioral features before imputation.