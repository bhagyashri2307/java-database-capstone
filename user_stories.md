User Story 1: Admin Login

Title:
As an admin, I want to log into the portal using my username and password, so that I can securely access and manage the platform.

Acceptance Criteria:
Admin should be able to enter a valid username and password.
Admin should be successfully logged in when valid credentials are provided.
Admin should receive an appropriate error message for invalid credentials.

Priority: High
Story Points: 3

Notes:
Login should be secured using authentication.
Only authorized admins should be able to access the admin portal.


User Story 2: Admin Logout

Title:
As an admin, I want to log out of the portal, so that I can protect the system from unauthorized access.

Acceptance Criteria:
Admin should be able to log out from the portal.
After logout, the admin session should be terminated.
Admin should be redirected to the login page after logout.

Priority: High
Story Points: 2

Notes:
Admin should not be able to access protected pages after logging out.


User Story 3: Add Doctor

Title:
As an admin, I want to add doctors to the portal, so that doctors can be registered and managed within the system.

Acceptance Criteria:
Admin should be able to enter the required doctor details.
Admin should be able to save the doctor's profile.
The newly added doctor should be stored in the system and visible in the doctor list.
The system should validate required doctor information before saving.

Priority: High
Story Points: 5

Notes:
Duplicate doctor records should be handled appropriately.
Required fields should not be left empty.


User Story 4: Delete Doctor

Title:
As an admin, I want to delete a doctor's profile from the portal, so that outdated or unwanted doctor records can be removed from the system.

Acceptance Criteria:
Admin should be able to view the list of doctors.
Admin should be able to select a doctor and delete their profile.
The system should ask for confirmation before deletion.
After deletion, the doctor's profile should no longer appear in the active doctor list.

Priority: High
Story Points: 3

Notes:
Deletion should be restricted to authorized admins.
Related appointment records should be handled according to the system's data-retention rules.


User Story 5: Monthly Appointment Statistics

Title:
As an admin, I want to run a stored procedure in MySQL CLI to get the number of appointments per month, so that I can track appointment usage statistics.

Acceptance Criteria:
Admin should be able to execute the stored procedure through MySQL CLI.
The stored procedure should calculate the number of appointments for each month.
The result should display the monthly appointment count.
The output should help the admin track platform usage statistics.

Priority: Medium
Story Points: 5

Notes:
The stored procedure should use the appointment data stored in the database.
Monthly counts should be calculated accurately based on the appointment date/time.

Patients:

User Story 1: View Doctors

Title:
As a patient, I want to view a list of doctors without logging in, so that I can explore available doctors before registering.

Acceptance Criteria:
Patient should be able to view the list of doctors without logging in.
The list should display relevant doctor information.
Patient should be able to browse available doctors before registration.

Priority: Medium
Story Points: 3

Notes:
Login should not be required to view doctors.
Only active doctors should be displayed.


User Story 2: Patient Registration and Login

Title:
As a patient, I want to register and log into the portal using my email and password, so that I can securely access and manage my appointments.

Acceptance Criteria:
Patient should be able to create an account using their email and password.
The system should validate the registration details.
Patient should be able to log in using their registered credentials.
The system should display an error message for invalid login credentials.
Duplicate email registration should not be allowed.

Priority: High
Story Points: 5

Notes:
Password should be stored securely.
Only authenticated patients should access appointment management features.


User Story 3: Book Appointment

Title:
As a patient, I want to log in and book a one-hour appointment with a doctor, so that I can consult with the doctor.

Acceptance Criteria:
Patient should be logged in to book an appointment.
Patient should be able to select a doctor.
Patient should be able to select an available time slot.
Each appointment should have a duration of one hour.
The system should confirm the appointment after successful booking.

Priority: High
Story Points: 5

Notes:
Only available time slots should be displayed.
An already booked slot should not be available for selection.


User Story 4: View Upcoming Appointments

Title:
As a patient, I want to view my upcoming appointments, so that I can prepare accordingly.

Acceptance Criteria:
Patient should be logged in to view appointments.
Patient should be able to view their upcoming appointments.
Appointment details should include the doctor, date, time, and status.
Only appointments belonging to the logged-in patient should be displayed.

Priority: Medium
Story Points: 3

Notes:
Past appointments should not appear in the upcoming appointments list.


User Story 5: Patient Logout

Title:
As a patient, I want to log out of the portal, so that I can secure my account after using the system.

Acceptance Criteria:
Patient should be able to log out from the portal.
The patient's session/authentication should be terminated after logout.
Patient should be redirected to the login page after logout.
Protected pages should not be accessible after logout.

Priority: High
Story Points: 2

Notes:
Logout should securely invalidate the patient's authentication.

Doctors:

User Story 1: Doctor Login & Logout

Title:
As a doctor, I want to log into and log out of the portal, so that I can securely manage my appointments and protect my data.

Acceptance Criteria:
Doctor should be able to log in using valid credentials.
The system should display an error for invalid credentials.
Doctor should be able to log out from the portal.
After logout, protected pages should not be accessible.

Priority: High
Story Points: 3

Notes:
Doctor authentication should be secure.


User Story 2: View Appointment Calendar

Title:
As a doctor, I want to view my appointment calendar, so that I can stay organized and manage my schedule.

Acceptance Criteria:
Doctor should be able to view their appointment calendar.
The calendar should display upcoming appointments.
Appointment details should include patient, date, time, and status.
Doctor should only see their own appointments.

Priority: High
Story Points: 5

Notes:
Upcoming and past appointments should be clearly distinguishable.


User Story 3: Manage Availability

Title:
As a doctor, I want to mark my unavailable time slots, so that patients can only view and book available slots.

Acceptance Criteria:
Doctor should be able to mark specific dates or time slots as unavailable.
Unavailable slots should not be shown to patients as bookable.
Patients should only be able to book available slots.
Doctor should be able to update their availability.

Priority: High
Story Points: 5

Notes:
Existing appointments should not be affected by availability updates.


User Story 4: Update Doctor Profile

Title:
As a doctor, I want to update my profile with my specialization and contact information, so that patients have up-to-date information.

Acceptance Criteria:
Doctor should be able to view their profile.
Doctor should be able to update their specialization.
Doctor should be able to update their contact information.
Updated information should be saved successfully.
Patients should be able to view the updated information.

Priority: Medium
Story Points: 3

Notes:
The system should validate profile information before saving.


User Story 5: View Patient Details

Title:
As a doctor, I want to view patient details for upcoming appointments, so that I can be prepared for the consultation.

Acceptance Criteria:
Doctor should be able to view patient details for upcoming appointments.
Doctor should only be able to access details of patients with their appointments.
Relevant patient information should be displayed.
Unauthorized users should not be able to access patient information.

Priority: High
Story Points: 3

Notes:
Patient information should be protected and accessible only to authorized doctors.
