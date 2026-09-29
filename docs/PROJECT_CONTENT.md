# Incident Lifecycle Automation in ServiceNow — Project Content

## 1. Project Description

The objective of this project is to automate and standardize the Incident Management lifecycle using ServiceNow's Incident module.

The project demonstrates how a Service Desk agent creates and classifies an incident, uses Agent Assist and Knowledge Management, reassigns the incident to Level 2 support, tracks SLAs and related records, handles a required change, creates a child incident, documents the cause and resolution, and creates a reusable knowledge article from the resolved incident.

### Key Goals

- Enable Service Desk agents to create and classify incidents.
- Integrate Knowledge Management for faster resolution.
- Allow reassignment to appropriate support groups.
- Enable Level 2 technicians to investigate and resolve incidents.
- Create emergency change requests directly from incidents.
- Allow child incident creation for tracking related or recurring issues.
- Generate knowledge articles from resolved incidents.
- Improve SLA compliance and service visibility.
- Support collaboration between Service Desk, Network, Change Management, and Knowledge teams.

---

## 2. Functional Scope

The functional scope includes:

- Incident Record Creation in Service Operations Workspace.
- Incident Classification using Category, Subcategory, Urgency, Service, Service Offering, and Configuration Item.
- Agent Assist Knowledge Integration.
- Reassignment to Level 2 Support Teams.
- Emergency Change Request Creation.
- Child Incident Creation.
- Incident Cause and Resolution Documentation.
- Knowledge Article Creation from Incident.
- SLA and Related Record Tracking.

---

## 3. Stakeholder Mapping

| Stakeholder | Role | Needs / Expectations | Impact of Automation |
|---|---|---|---|
| End Users | Report IT issues | Quick resolution and visibility | Faster issue resolution and transparent tracking |
| Service Desk Agents | First-level support | Easy logging and classification tools | Standardized intake and faster escalation |
| Level 2 Support (Network/Hardware Teams) | Diagnose and resolve issues | Complete incident data and related records | Better diagnosis and clear task ownership |
| Change Management Team | Handle emergency changes | Structured change requests | Integrated change control |
| ServiceNow Admin | Maintain configuration | Scalable and trackable solution | Controlled process management |

---

## 4. Project Milestones and Skills

### Milestones

1. Incident Record Creation
2. Incident Classification
3. Knowledge Integration
4. Reassignment & Escalation
5. Change Request Creation
6. Child Incident Creation
7. Incident Resolution
8. Knowledge Creation
9. SLA & Related Record Validation

### Skills / ServiceNow Features

- Incident Management
- Agent Assist
- Change Management Integration
- Related Lists
- SLAs
- Knowledge Management
- Service Operations Workspace
- CMDB / Configuration Items

---

## 5. Service Configuration

If admin access is available, create the service.

### Remote Access Service

Navigation: **All → Search → cmdb_ci_service.LIST → New**

Fill the details:

- **Name:** Remote Access
- **Operational status:** Operational
- Click **Submit**.

### Corporate VPN Service Offering

Navigation: **All → Search → service_offering.LIST → New**

Fill the details:

- **Name:** Corporate VPN
- **Parent:** Remote Access
- **Operational status:** Operational
- Click **Submit**.

The Service Offering is associated with the Remote Access service so that the incident can be classified using the correct service hierarchy.

---

## 6. Incident Record Creation

Open ServiceNow and impersonate **Beth Anglin**.

Navigate to:

**Service Operations Workspace → List → Incidents → Open**

Click **New**.

Enter:

- **Short description:** Unable to connect to Corporate VPN from home office
- **Caller:** Michael Hoefer

Click **Save**.

Go to the **Details** tab.

Set:

- **Assignment group:** Service Desk

Click **Save**.

The incident created for this project is **INC0010001**.

---

## 7. Incident Classification

Stay in the same incident and open the **Details** tab.

Update the following:

- **Description:** Michael advised he was able to connect yesterday evening, but this morning received an authentication error. The Internet works fine.
- **Channel:** Phone
- **Category:** Network
- **Subcategory:** VPN
- **Urgency:** 2 - Medium
- **Service:** Remote Access
- **Service Offering:** Corporate VPN
- **Configuration Item:** ThinkStationS20 (or another available applicable CI)

In the Compose section, add the following work note:

> Classified and assigned incident.

Click **Assign to me** and **Save**.

This classification ensures that the incident contains the information needed for routing, prioritization, investigation, and SLA tracking.

---

## 8. Agent Assist and Knowledge Integration

Click **Agent Assist** on the right-side panel.

Ensure **Knowledge Articles** are selected.

Verify that knowledge articles appear based on the incident short description.

Open one of the suggested articles.

From the article's three-dot menu:

1. Select **Mark Article as Helpful**.
2. Click **Attach Article**.
3. Add the comment:
   > Follow the Steps and Resolve the Incident.
4. Select **Attach Article**.

Return to the incident.

### Verification

Verify that:

- The knowledge article is linked in the Activity log.
- The helpful indicator is marked.
- The attachment/comment is recorded.

This step demonstrates how Agent Assist can reduce investigation time by presenting contextual knowledge directly inside the incident workspace.

---

## 9. Watch List and Work Notes List

In the **Details** tab:

- Add **Samantha Bordwell** to the **Watch list** so she can track the incident and receive updates.
- Add **Beth Anglin** to the **Work notes list** so she can follow work notes and stay updated on the incident resolution.

If any mentioned member cannot be found, select another available member.

These lists support collaboration and keep relevant users informed while the incident is transferred to another support team.

---

## 10. Reassignment to Level 2 Support

Update the **Assignment group** to:

**Network**

Verify that the **Assigned to** field clears automatically.

Click **Save**.

The incident is now routed to the Network team for further technical investigation and resolution.

---

## 11. Level 2 Investigation

Impersonate **David Loo**.

Select the three dots on the banner → **Workspaces** → **Service Operations Workspace → Incidents → Open**.

Open the VPN incident.

Click **Assign to me**.

Verify:

- Description is visible.
- Knowledge articles are visible.
- SLA is visible in **Task SLAs** in the Related Records section.

This confirms that the Level 2 technician can access the complete incident context and monitor SLA information.

---

## 12. Configuration Item Update and On Hold State

Update the Configuration Item from **ThinkStation** to **PowerEdge**.

Click **Save**.

Return to the incident and update:

- **State:** On Hold
- **On Hold Reason:** Awaiting Change

Click **Save**.

The On Hold state represents a dependency on a required change before the incident can be fully resolved.

---

## 13. Child Incident Creation

From **Related Records → Child Incidents → New** create a child incident.

Enter:

- **Short Description:** Unable to connect to Corporate VPN
- **Caller:** Select any available user
- **Description:** User receiving VPN authentication failure error.

Click **Save** and make note of the generated incident number.

Return to the parent incident and open **Related Records**.

Verify that the child incident is listed under Child Incidents.

This demonstrates parent-child incident tracking for related or recurring issues.

---

## 14. Cause Documentation

On the **Overview** tab, add the Cause.

### Probable Cause

> PowerEdge service was suspended and required restart.

Click **Save**.

The cause documents the technical finding that explains why the VPN incident occurred.

---

## 15. Incident Resolution

Add a Resolution.

### Resolution Code

**Workaround provided**

### Resolution Notes

> Restarted VPN-SRV-02 service as per emergency change request.

Save the resolution.

Click **Resolve**.

Confirm the popup by clicking **Resolve**.

The parent incident is now resolved with structured cause and resolution information.

---

## 16. Knowledge Article Creation

Click **Create Knowledge**.

Select:

- **Knowledge Base:** IT
- **Article Template:** Standard

Click **Next**.

Verify all details and click **Save**.

Return to the Parent Record.

Open **Related Records → Created Knowledge**.

Verify that the created Knowledge Article is listed.

This converts the resolved incident into reusable organizational knowledge that can support future VPN incidents.

---

## 17. Final Validation

Verify the following end-to-end results:

- Parent incident state = **Resolved**.
- Child incident state = **Resolved**.
- Activity shows resolution triggered by the parent.
- Change request is linked.
- Knowledge article is created.
- SLA tracking is visible.
- Incident cause is documented.
- Resolution code and resolution notes are documented.
- Parent-child relationship is visible in Related Records.
- Knowledge article is available for future troubleshooting.

---

## 18. Scenario Validation

This scenario validates:

- Incident lifecycle end-to-end.
- Escalation process.
- Change integration.
- Knowledge creation.
- Child incident management.
- SLA tracking.
- Multi-team collaboration.
- Structured cause and resolution documentation.

---

## 19. Conclusion

This project demonstrates a complete Incident Management lifecycle automation in ServiceNow.

Service Desk agents can log and classify incidents, leverage knowledge for faster resolution, escalate to Level 2 teams, initiate emergency changes, and document final resolution properly.

The integration between Incident, Change, and Knowledge modules ensures structured issue management, improved SLA adherence, better visibility, and more effective IT service delivery.

---

## 20. Repository Evidence

Screenshots captured from the ServiceNow project should be stored in the `screenshots/` folder and referenced in the README or this document. Suggested evidence includes incident creation, classification, Agent Assist, watch list, reassignment, Level 2 investigation, configuration item update, On Hold state, child incident, cause, resolution, and knowledge creation/final validation.
