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
