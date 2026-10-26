# Recruitment-Process-in-SAP-S-4HANA
A step-by-step walkthrough of the end-to-end recruitment workflow in **SAP S/4HANA Human Resource Management (HRM)**, from setting up the organization structure to hiring a new employee and verifying the result.

# Recruitment Process in SAP S/4HANA

A step-by-step walkthrough of the end-to-end recruitment workflow in **SAP S/4HANA Human Resource Management (HRM)**, from setting up the organization structure to hiring a new employee and verifying the result. Built as a Group 6 academic project.

## Objective

The project aimed to demonstrate how recruitment is handled in SAP S/4HANA HRM by working through the full process hands-on: building the organizational structure, defining the skills each position requires, and hiring an employee into the right position. The exercise shows how the Organizational Management, Personnel Development, Recruitment, and Personnel Administration modules work together, and gives practical experience with the transaction codes used in everyday HR work.

### Skills Learned

- Understanding how the recruitment process is structured and integrated across SAP HR modules.
- Creating and maintaining organizational units and positions.
- Building a qualification catalog and assigning qualifications to positions.
- Defining career paths and position requirements.
- Hiring an employee using personnel actions and creating the HR master record.
- Verifying data and organizational placement after hiring.
- Navigating SAP using menu paths and transaction codes.

### Tools Used

- **SAP S/4HANA (HRM)** as the main system for all configuration and hiring steps.
- **SAP GUI** for working with the transactions listed below.
- **Microsoft PowerPoint** for documenting the process and screenshots.

### Transaction Codes at a Glance

| T-Code | Purpose |
|--------|---------|
| `PPOME` | Create and change organizational units and positions |
| `OOQA` | Edit the qualifications catalog |
| `PPPM` | Maintain profiles (assign qualifications and requirements to positions) |
| `PB40` | Applicant actions (prepare the hiring from the recruitment side) |
| `PA40` | Personnel actions (hire the employee) |
| `PA10` | Display the personnel file to verify data |
| `PPOSE` | Display the organization and staffing structure |

## Process Overview

The workflow runs in four phases:

1. **Organizational planning:** set up departments and positions.
2. **Requirement management:** define the qualifications each position needs.
3. **Career definition (optional):** map progression paths between positions.
4. **Hiring execution:** hire the employee and confirm the result.

## Steps

### 1. Organizational Setup

Navigate to *Human Resources → Organizational Management → Organizational Plan → Organization and Staffing → Change* (`PPOME`).

- Set the validity date to **2025.04.01**.
- Create sub organizational units under the Security organizational unit: **Plant Security** and **IT Security**.
- Move the existing **Security Guard** and **Security Manager** positions under Plant Security.
- Create two new positions under IT Security, **Senior IT Admin** and **Junior IT Admin**, using the relationship *Incorporates (Position)*.

*Ref 1: Organizational structure after setup*

![Organizational Structure](images/org-structure.png)

### 2. Create Qualifications

Navigate to *Human Resources → Personnel Development → Settings → Current Settings → Edit Qualifications Catalog* (`OOQA`).

- Create a new qualification group, **Soft Skills**, with a point scale of 1 to 3.
- Create the qualification **IT Affinity** inside this group.

*Ref 2: Qualifications catalog*

![Qualifications Catalog](images/qualification-catalog.png)

### 3. Assign Qualifications to Positions

Navigate to *Human Resources → Personnel Management → Personnel Development → Profile → Change* (`PPPM`).

- Use **Structure Search** to find the position under the organizational unit.
- Assign **IT Affinity** to both **Senior IT Admin** and **Junior IT Admin** using *Create*.
- Where needed, set proficiency or priority levels and validity dates (for example, "Essential" versus "Nice to Have").

### 4. Career Planning (Optional)

Navigate to *Human Resources → Personnel Management → Personnel Development → Settings → Current Settings → Edit Careers*.

- Choose a predefined career template or create a custom one.
- Define sequential career steps, such as Security Guard → Security Manager, with a recommended duration for each role.

### 5. Hire a New Employee

Navigate to *Human Resources → Personnel Management → Administration → HR Master Data → Personnel Actions* (`PA40`).

- Select the action **Hiring (TE mini master)**.
- Set the organizational parameters: Personnel Area `DL00`, Employee Group `1`, Employee Subgroup `U4`.
- Use **Structure Search** to select the **Senior IT Admin** position.
- Enter the personal data (title, name, date of birth, gender, ID number) and set the start date to **2025.04.01**.
- Change the subarea to `EX00`, then enter the address details.
- Save and confirm the action.

For hiring from the recruitment side, the applicant is first prepared in `PB40` (application number and hiring start date), then converted to an employee in `PA40`.

*Ref 3: Hiring action in PA40*

![Hiring Action](images/hiring-action.png)

### 6. Verification

- **`PA10`:** enter the new employee number and choose *Display* to confirm all data was saved correctly.
- **`PPOSE`:** open the organization and staffing view to confirm the employee appears under the correct organizational unit and position.

*Ref 4: Final overview of the staffed organization*

![Final Overview](images/final-overview.png)

## System Behavior Notes

- **Green checkmarks** indicate a correct entry or progression to the next step.
- **Warnings** may appear at some steps and are usually cleared by pressing *Enter*.
- **Mandatory fields** such as position, date, personal details, and region must be filled in before saving.
- **Employee number:** note it down, since it is needed for later steps like `PA10`.

> Personal and sensitive values shown in the screenshots (such as names and ID numbers) are placeholders or masked for demonstration.

## Key Takeaways

- Follow the logical progression from organizational setup to qualifications to hiring.
- Learn the core transaction codes (`PPOME`, `PPPM`, `PB40`, `PA40`, `PA10`, `PPOSE`) for faster navigation.
- Accurate data entry prevents errors later in the process.

## Team (Group 6)

| Member | ID | Contribution |
|--------|----|--------------|
| Sunilkumar Amarjith | M24W0187 | Carried out the SAP S/4HANA implementation (organizational units, qualifications, hiring) and prepared the presentation |
| Sanjay Kandel | M23W0061 | Coordinated the team and verified results against SAP reference materials |
| M.A.G.C. Sandaruwan | M23W7397 | Assisted with data entry, process flow accuracy, and documentation |

## References

- Materials from the SAP Portal
- Human Resource Management System Development modules
