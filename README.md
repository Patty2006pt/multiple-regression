# Salary Prediction with Multiple Linear Regression
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

โปรเจกต์สาธิตการสร้างโมเดล Machine Learning ด้วย Python และ Scikit-Learn เพื่อทำนายเงินเดือนพนักงานจากปัจจัยด้านประสบการณ์ วุฒิการศึกษา และทักษะภาษาอังกฤษ พร้อมแสดงผลการประเมินโมเดลผ่านกราฟเปรียบเทียบ
## 🚀 Features
- 📊 สร้างโมเดล Multiple Linear Regression ทำนายเงินเดือนจากตัวแปรอิสระหลายตัว
- 📈 แสดงผลลัพธ์ค่าสัมประสิทธิ์ (Coefficients) และจุดตัดแกน (Intercept)
- 📉 สร้างกราฟ Scatter Plot เปรียบเทียบระหว่างเงินเดือนจริง (Actual Salary) และเงินเดือนที่โมเดลคาดการณ์ (Predicted Salary)

## 🛠️ Tech Stack
- **Language:** Python 3.9+
- **Libraries:**
  - `pandas` (สำหรับการจัดการชุดข้อมูล)
  - `scikit-learn` (สำหรับสร้างโมเดล Linear Regression)
  - `matplotlib` (สำหรับการวาดกราฟแสดงผล)
 
## ⚙️ Getting Started

### Prerequisites
ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Python ไว้ในเครื่องแล้ว จากนั้นติดตั้งไลบรารีที่จำเป็น:

```bash
pip install pandas scikit-learn matplotlib

## Installation and running
- โคลนโปรเจกต์นี้ลงในเครื่องของคุณ หรือคัดลอกโค้ดไปรันใน Jupyter Notebook / Google Colab
- รันสคริปต์เพื่อสร้างโมเดลและแสดงผลการทำนาย
python multiple_regression.py

📖 Usage
ตัวอย่างโค้ดส่วนหนึ่งในการเรียกใช้งานโมเดลเพื่อทำนายเงินเดือนสำหรับพนักงานใหม่:

import pandas as pd
from sklearn.linear_model import LinearRegression

# ข้อมูลตัวอย่าง
data = {
    "experience": [1, 3, 5, 7, 9, 2, 4, 6],
    "education":  [1, 1, 2, 2, 3, 1, 2, 3],
    "english":    [3, 5, 6, 7, 8, 4, 6, 9],
    "salary":     [18000, 22000, 30000, 35000, 50000, 20000, 32000, 55000]
}

df = pd.DataFrame(data)
X = df[["experience", "education", "english"]]
y = df["salary"]

# เทรนโมเดล
model = LinearRegression()
model.fit(X, y)

# ทำนายเงินเดือน (เช่น: ประสบการณ์ 5 ปี, ป.โท [วุฒิ 2], ทักษะภาษาอังกฤษ = 7)
new_person = [[5, 2, 7]]
predicted_salary = model.predict(new_person)
print("เงินเดือนที่คาดการณ์:", predicted_salary[0])
