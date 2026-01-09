# Design Document

## Purpose
This document describes the data model for the PSNM Innovations frontend.
The design is based on the available UI screens and wireframes.

---

## PSNM XperienceOS – Landing and Role Selection Page

### PlatformOverview
Stores basic information shown on the landing section.

**Properties**
- id
- title
- tagline
- description
- projectsCount
- partnersCount
- mentorsCount
- certificatesCount

**Methods**
- updateMetrics()

---

### UserRole
Represents the roles displayed for user selection.

**Properties**
- id
- name
- description
- displayOrder
- isSelectable

**Methods**
- selectRole()

---

### RoleType
Defines the available role types.

**Values**
- ProjectPartner
- Mentor
- CollegeInstitutionAdmin
- IndustryMSMEPartner
- InternalDeliveryTeam
- FounderAccess

---

### CallToAction
Represents the main action button on the page.

**Properties**
- id
- label
- actionType

**Methods**
- execute()

---

### ExternalLink
Represents links that redirect users to external websites.

**Properties**
- id
- label
- url
- opensInNewTab

**Methods**
- navigate()

---

### Relationships
- PlatformOverview is shown on the landing page
- Multiple UserRole options are displayed for selection
- Each UserRole maps to a RoleType
- CallToAction is used to proceed from the role selection page
- ExternalLink is used for navigation to external sites

---

## PSNM Innovations – Main Website Navigation

### NavigationBar
Represents the top navigation bar of the website.

**Properties**
- id
- brandName
- logo


**Methods**
- navigateTo()

---

### NavigationItem
Represents items shown in the navigation bar.

**Properties**
- id
- label
- route
- displayOrder
- isDropdown

**Methods**
- navigate()

---

### NavigationDropdown
Represents dropdown menus under navigation items.

**Properties**
- id
- parentNavigationItemId
- label
- displayOrder

**Methods**
- open()
- close()

---

### NavigationLink
Represents links inside dropdown menus.

**Properties**
- id
- label
- route
- displayOrder

**Methods**
- navigate()

---

### Relationships
- NavigationBar contains multiple NavigationItems
- NavigationItems may have NavigationDropdowns
- NavigationDropdowns contain NavigationLinks
- Navigation links route to corresponding website pages
