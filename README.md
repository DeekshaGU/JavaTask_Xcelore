# JavaTask_Xcelore
We have a platform where doctors can register their patients through a mobile or web portal. For this to work we need to build backend APIs to achieve task like: 
◦ Adding a doctor &amp; their speciality 
◦ Adding a patient &amp; it’s symptom
◦ Suggesting the doctor based on patient’s symptom
 # 🏥 Doctor-Patient Platform - Spring Boot + Hibernate



This project is a Spring Boot-based backend system for managing doctors and patients. It includes functionalities to register doctors and patients, and to suggest appropriate doctors based on a patient's symptoms and location.

---

## 📌 Features

- ✅ Add and delete doctors with specialization and city
- ✅ Add and delete patients with symptoms and city
- ✅ Suggest **doctors** based on patient’s symptom and city
- ✅ Field validation for name, email, phone, and city
- ✅ Handles edge cases (city not supported, doctor not available for symptom)
- ✅ RESTful API with Spring Boot , Hibernate, and JPA
- ✅ API documentation via Swagger

---

## 🛠️ Tech Stack

- Java 
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- Hibernate ORM
- H2 / MySQL database
- Bean Validation (Jakarta Validation)
- Springdoc OpenAPI for Swagger
- Postman for API testing

---

## 🧾 Entities

### 👨‍⚕️ Doctor
- `name` (min 3 characters)
- `city`: `Delhi`, `Noida`, `Faridabad`
- `email` (valid format)
- `phone` (min 10 digits)
- `speciality`: `Orthopaedic`, `Gynecology`, `Dermatology`, `ENT`

### 👩‍🦰 Patient
- `name` (min 3 characters)
- `city` (max 20 characters)
- `email` (valid format)
- `phone` (min 10 digits)
- `symptom`: 
  - Orthopaedic: `Arthritis`, `Back Pain`, `Tissue injuries`
  - Gynecology: `Dysmenorrhea`
  - Dermatology: `Skin infection`, `Skin burn`
  - ENT: `Ear pain`

---

## 🔁 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/doctors` | Add a doctor |
| `DELETE` | `/doctors/{id}` | Remove a doctor |
| `POST` | `/patients` | Add a patient |
| `DELETE` | `/patients/{id}` | Remove a patient |
| `GET` | `/suggest-doctor/{patientId}` | Suggest doctors based on patient symptom and city |

---

## ❗ Edge Case Handling

- If patient’s city is **not Delhi, Noida, or Faridabad**:
  - **Response**: `"We are still waiting to expand to your location"`

- If **no doctors are found** in the location for the symptom:
  - **Response**: `"There isn’t any doctor present at your location for your symptom"`

---

## 🚀 Run Locally

### Step 1: Clone the repo
```bash
git clone https://github.com/yourusername/doctor-patient-platform.git
cd doctor-patient-platform
