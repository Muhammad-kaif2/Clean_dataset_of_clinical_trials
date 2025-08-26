# Clinical Trials Data Cleaning  

## 📌 Project Summary  
This dataset contains information about **500 patients**, of which **350 participated in a clinical trial**. Prior to the trial, none of the patients were using **Novodra** (injectable insulin) or **Auralin** (oral insulin under research) as their primary insulin source. All patients had elevated **HbA1c levels**.  

During the trial:  
- All **350 patients were initially treated with Novodra** to establish baseline HbA1c and insulin dose.  
- After **4 weeks**:  
  - **175 patients switched to Auralin** for 24 weeks.  
  - **175 patients continued Novodra** for 24 weeks.  

Data regarding **adverse effects** was also recorded.  

---

## 🛠️ Data Cleaning Steps (Step by Step)  
1. **Duplicate Records Removal** → Removed duplicate patient rows.  
2. **Missing Values Handling** → Addressed missing values in `birthdate`, `weight`, `height`, `BMI`, and `adverse_effects` via imputation or removal.  
3. **Data Type Fixing** →  
   - Converted `birthdate` to proper datetime.  
   - Ensured numeric types for `weight`, `height`, `BMI`, and HbA1c levels.  
4. **Standardization** → Capitalized and standardized columns like `given_name` and `surname`.  
5. **Merge & Integration** → Merged **patients** and **treatments** datasets on `patient_id` (or `given_name`, `surname`) to create a consolidated dataset.  
6. **Outlier Detection** → Identified extreme values (e.g., `BMI > 70`, `HbA1c < 3`) for further review.  

---

## 📊 Column Descriptions  
- **patient_id** → Unique identifier for each patient.  
- **given_name, surname** → Patient’s name.  
- **assigned_sex** → Male / Female.  
- **birthdate** → Date of birth.  
- **weight** → Patient’s weight (kg).  
- **height** → Patient’s height (cm).  
- **bmi** → Body Mass Index (calculated).  
- **hba1c_level** → Measure of blood sugar control.  
- **treatment_group** → Assigned group (Novodra / Auralin).  
- **adverse_effects** → Side effects reported (Yes/No).  
- **treatment_start_date** → Trial start date.  
- **treatment_end_date** → Trial end date.  

---

## ⚠️ Issues with the Dataset  
- **Missing Values** → Some patients have missing `weight`, `height`, or `BMI`.  
- **Inconsistent Names** → Mixed case values in `given_name` and `surname`.  
- **Incorrect Dates** → Unrealistic birthdates (e.g., future dates).  
- **Outliers** → Extreme values in `HbA1c`, `BMI`, and `weight`.  
- **Adverse Effects Standardization** → Variations like `"yes"`, `"Yes"`, `"Y"` need normalization.  
