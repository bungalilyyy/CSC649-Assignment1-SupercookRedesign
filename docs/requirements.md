# Requirements and User Stories

## Functional Requirements (FR)

| ID | Functional Requirement Statement | Testability Method |
| :--- | :--- | :--- |
| **FR1** | The system shall allow users to add ingredients from their pantry| Verified by entering an ingredient name and checking its appearance in the pantry inventory list |
| **FR2** | The system shall allow users to mark each pantry ingredient as available or out of stock. | Verified by clicking the stock toggle and confirming the visual availability state updates. |
| **FR3** | The system shall exclude out-of-stock pantry ingredients when suggesting new recipes based on a user’s search. | Verified by marking an item out-of-stock and performing a recipe query to ensure no recipes require that item. |
| **FR4** | The system shall display substitution suggestions when an approved rule exists for the selected missing ingredients and recipe context. | Verified by selecting a recipe with a missing ingredient and confirming valid substitutes are listed. |
| **FR5** | The system shall list the missing ingredients for each displayed recipe. | Verified by viewing a recipe detail page and checking the highlighted missing items list. |
| **FR6** | The system shall allow users to save a recipe to their favourites. | Verified by clicking the favourite icon and checking its presence in the Favourites tab. |
| **FR7** | The system shall restore locally saved pantry data when the application is reopened. | Verified by force-closing the app and confirming pantry items persist upon relaunch[. |
| **FR8** | The system shall synchronize a signed-in user’s pantry changes across devices when an internet connection is available. | Verified by making a pantry edit on Device A and checking automatic sync on Device B. |
| **FR9** | The system shall display whether pantry changes are saved locally, pending synchronization, or synchronized. | Verified by checking status badges during offline mode, sync-in-progress, and completed states. |
| **FR10** | The system shall allow users to search for recipes without creating an account. | Verified by launching the app as a guest and executing a recipe search without logging in. |

---

## B2. Non-Functional Requirements (NFR)

| ID | Type | Non-Functional Requirement Statement | Measurement |
| :--- | :--- | :--- | :--- |
| **NFR1** | Performance | For a dataset of 1,000 recipes containing up to 30 ingredients, the system shall display matching search results within 5 seconds. | Measured using API response timers under normal operating conditions. |
| **NFR2** | Usability | At least 4 out of 5 first-time test participants shall add three ingredients and open a matching recipe within 2 minutes without assistance. | Measured via usability testing task completion rates and time-on-task metrics. |
| **NFR3** | Reliability | The system shall display a "saved locally" confirmation message whenever restoring all pantry entries and their availability states without data loss. | Verified by testing app restarts under offline conditions across test iterations. |
| **NFR4** | Synchronization | With both devices online and no simultaneous edits, a confirmed pantry change shall appear on the second signed-in device within 10 seconds in at least 19 of 20 trials. | Verified using cross-device sync trial logs. |



## User Stories and Acceptance Criteria

### User Story 1 (Linked to FR8 & FR9)
* **User Story:** As a home cook, I want my pantry list changes to synchronize automatically across my mobile and laptop,
* so that I can manage my meal plans seamlessly without losing data when switching anotherdevices.
* **Acceptance Criteria:**
  1. Editing a pantry item on one logged-in device updates the cloud database and reflects on the second device within 10 seconds.
  2. If the user is offline, the application displays a "Saved Locally" status indicator and automatically pushes changes to the cloud upon reconnection.

### User Story 2 (Linked to FR2 & FR3)
* **User Story:** As a grocery planner, I want to toggle missing pantry items as out-of-stock,
* so that the app only suggests recipes I can actually prepare without buying extra items.
* **Acceptance Criteria:**
  1. Toggling an ingredient to "Out-of-Stock" immediately excludes recipes requiring that specific item from current search recommendations.
  2. Re-toggling the ingredient to "Available" restores relevant recipe recommendations automatically.

### User Story 3 (Linked to FR10)
* **User Story:** As a first-time visitor, I want to search for recipes immediately in Guest Mode without registering an account,
* so that I can test the app’s features quickly without sign-up friction.
* **Acceptance Criteria:**
  1. Clicking "Continue as Guest" bypasses the login screen and navigates straight to the main recipe search page.
  2. Guest users can input up to 5 ingredients and view matching recipe lists without being blocked by registration popups.
