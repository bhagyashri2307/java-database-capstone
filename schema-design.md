# Clinic Database Schema Design

## MySQL Database Design

MySQL will be used for structured clinic data such as patients, doctors, appointments, and administrators. The relationships between these entities require validation and referential integrity.

### Table: patients

* `id`: INT, Primary Key, Auto Increment
* `name`: VARCHAR(100), Not Null
* `email`: VARCHAR(150), Not Null, Unique
* `password`: VARCHAR(255), Not Null
* `phone`: VARCHAR(15), Not Null
* `created_at`: DATETIME, Not Null

### Table: doctors

* `id`: INT, Primary Key, Auto Increment
* `name`: VARCHAR(100), Not Null
* `email`: VARCHAR(150), Not Null, Unique
* `password`: VARCHAR(255), Not Null
* `specialization`: VARCHAR(100), Not Null
* `phone`: VARCHAR(15), Not Null
* `created_at`: DATETIME, Not Null

### Table: appointments

* `id`: INT, Primary Key, Auto Increment
* `doctor_id`: INT, Foreign Key → `doctors(id)`, Not Null
* `patient_id`: INT, Foreign Key → `patients(id)`, Not Null
* `appointment_time`: DATETIME, Not Null
* `duration_minutes`: INT, Not Null, Default 60
* `status`: VARCHAR(20), Not Null, Default 'SCHEDULED'
* `created_at`: DATETIME, Not Null

**Constraints and design decisions:**

* A doctor should not have overlapping appointments.
* A patient should not be able to book the same time slot with multiple doctors.
* Appointments should not be automatically deleted when a patient or doctor is removed, because past appointment history may need to be retained.
* Doctor and patient records can be handled using a soft-delete or inactive status when historical appointments need to be preserved.
* Email addresses should be unique.
* Email and phone format validation can be performed in the application code.

### Table: admin

* `id`: INT, Primary Key, Auto Increment
* `username`: VARCHAR(100), Not Null, Unique
* `password`: VARCHAR(255), Not Null
* `created_at`: DATETIME, Not Null

### Table: doctor_availability

* `id`: INT, Primary Key, Auto Increment
* `doctor_id`: INT, Foreign Key → `doctors(id)`, Not Null
* `available_date`: DATE, Not Null
* `start_time`: TIME, Not Null
* `end_time`: TIME, Not Null
* `is_available`: BOOLEAN, Not Null, Default TRUE

**Design decision:**

* Doctor availability is stored separately so doctors can mark specific dates or time periods as unavailable.
* Patients should only be shown appointment slots that fall within the doctor's available schedule.

---

## MongoDB Collection Design

MongoDB will be used for flexible data that may vary between appointments, such as prescriptions and doctor notes. A prescription is associated with a specific appointment and can contain different medications, instructions, and additional metadata.

### Collection: prescriptions

```json
{
  "_id": "ObjectId('64abc123456')",
  "appointmentId": 101,
  "patientId": 25,
  "doctorId": 8,
  "prescribedAt": "2026-09-23T10:30:00Z",
  "doctorNotes": "Patient should take adequate rest and stay hydrated.",
  "medications": [
    {
      "name": "Paracetamol",
      "dosage": "500mg",
      "frequency": "Twice a day",
      "duration": "3 days",
      "instructions": "Take after meals"
    },
    {
      "name": "Vitamin D3",
      "dosage": "1000 IU",
      "frequency": "Once a day",
      "duration": "30 days",
      "instructions": "Take after breakfast"
    }
  ],
  "tags": [
    "follow-up",
    "general-consultation"
  ],
  "metadata": {
    "followUpRequired": true,
    "followUpDate": "2026-10-07",
    "priority": "normal"
  }
}
```

**Design decision:**

* Prescriptions are stored in MongoDB because their structure can vary between appointments.
* Multiple medications can be embedded in a single prescription document.
* Additional fields such as doctor notes, tags, attachments, or follow-up information can be added without changing a fixed relational schema.
* `appointmentId`, `patientId`, and `doctorId` connect the prescription document logically to the corresponding MySQL records.
