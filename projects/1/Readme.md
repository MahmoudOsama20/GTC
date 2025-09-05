# 🏨 Hotel Booking Cancellations – Data Cleaning & Preprocessing

## 📌 Project Overview
This project is part of **GTC ML Project 1 – Data Cleaning & Preprocessing Challenge**.  
The goal is to prepare a **raw hotel booking dataset** for machine learning, ensuring it is clean, consistent, and ready for modeling.  

The dataset comes from a Property Management System (PMS) and contains booking information, including customer details, reservation status, and booking behaviors.  

The **business problem**:  
➡️ Last-minute booking cancellations significantly affect hotel profitability.  
➡️ A well-prepared dataset is the foundation for building a robust prediction model to minimize these losses.

---

## 🗂️ Project Phases

### **Phase 1: Exploratory Data Analysis (EDA)**
- Generated dataset summary statistics (`.describe()`, `.info()`).
- Identified missing values and their percentages.
- Visualized missing data patterns.
- Detected outliers in key numeric columns (`adr`, `lead_time`) using boxplots and IQR.

### **Phase 2: Data Cleaning**
- **Missing Values Handling**:  
  - `company` & `agent` → filled with `0`.  
  - `country` → imputed with the most frequent value (mode).  
  - `children` → filled with median.  
- **Duplicates**: Removed duplicate rows.  
- **Outliers**:  
  - Capped extreme `adr` values at 1000.  
  - Capped unreasonable `lead_time` values.  
- **Data Types**: Converted date columns to `datetime`.  

### **Phase 3: Feature Engineering & Preprocessing**
- Created new features:  
  - `total_guests = adults + children + babies`  
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`  
  - `is_family = binary flag if booking includes children or babies`  
- Encoded categorical variables:  
  - One-Hot Encoding for low-cardinality features (e.g., `meal`, `market_segment`).  
  - Grouped rare categories in `country` as `"Other"`.  
- Removed **data leakage** by dropping `reservation_status` and `reservation_status_date`.  
- Finalized the dataset by splitting into **train/test sets**.

---

## 📊 Technologies Used
- **Python**
- **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**
- **Scikit-learn**

---

## 🚀 Next Steps
- Use this cleaned dataset to train machine learning models.  
- Evaluate predictive performance for cancellation classification.  
- Optimize features and model selection for business impact.  