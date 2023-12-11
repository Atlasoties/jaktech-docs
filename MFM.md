# Tables and Relationships Overview for MFM Tender System:
[Schema Diagram - MFM Tender System](https://www.figma.com/file/R7hLiowZvIODEwfIXXNKNr/MFM-Tender-System?type=whiteboard&node-id=0%3A1&t=uUiNYR0seEd5qUVu-1)

Note: Please refer to the Figma link for the updated schema diagram.
## Role Table:

**Description:** Stores user roles within the system.

**Relationships:**
- Many-to-Many with Permissions (Permission_Role).
- Many-to-Many with Users (Role_User).
## Permissions Table:

**Description:** Contains various permissions available in the system.

**Relationships:**
- Many-to-Many with Roles (Permission_Role).
## Permission_Role Table:

**Description:** Associates roles with their corresponding permissions.

**Relationships:**
- Many-to-One with Roles.
- Many-to-One with Permissions.
## Role_User Table:

**Description:** Establishes a relationship between users and their assigned roles.

**Relationships:**
- Many-to-One with Roles.
- Many-to-One with Users.
## User Table:

**Description:** Stores information about users in the system.

**Relationships:**
- Many-to-Many with Roles (Role_User).
- One-to-Many with Applications (Applications).
## Company Table:

**Description:** Contains details about companies participating in the tendering process.

**Relationships:**
- One-to-Many with Tenders (Tender).
## Applications Table:

**Description:** Stores information about applications submitted for tenders.

**Relationships:**
- Many-to-One with Users.
- Many-to-One with Tenders.
## Tender Table:

**Description:** Contains details about individual tenders.

**Relationships:**
- Many-to-One with Companies.
- Many-to-One with Tender Categories (Tender_Categories).
- One-to-Many with Applications.
## Tender_Categories Table:

**Description:** Defines categories for grouping tenders.

**Relationships:**
- One-to-Many with Tenders.
## Categories Table:

**Description:** Stores general categories used in the system.
## Countries Table:

**Description:** Stores information about countries.

**Relationships:**
- One-to-Many with Regions (Regions).
## Regions Table:

**Description:** Defines regions within countries.

**Relationships:**
- Many-to-One with Countries.
## Media_Library Table:

**Description:** Manages media files associated with the tendering system.

## Activity_Logs Table:

**Description:** Logs activities and changes within the system.

**Relationships:**
- Polymorphic relationships with various tables (e.g., Users, Tenders).