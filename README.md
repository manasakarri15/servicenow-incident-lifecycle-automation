# Incident Lifecycle Automation in ServiceNow

## Student Details

| Field | Value |
|-------|-------|
| **Student Name** | Manasa Karri |
| **Course** | B.Tech – Data Science |
| **College** | ISTS Women's Engineering College |
| **Academic Year** | 2026–2027 |
| **Project Environment** | SkillWallet → ServiceNow |

---

## Project Overview

This project demonstrates a comprehensive **Incident Management lifecycle automation** in ServiceNow, focusing on ITSM best practices. The project covers the complete incident lifecycle from initial creation through resolution, integrating knowledge management, change control, and escalation workflows.

**Key Incident Details:**
- **Incident Number:** INC0010001
- **Short Description:** Unable to connect to Corporate VPN from home office
- **Caller:** Michael Hoefer
- **Location:** SHS quadra 5, Bloco E
- **Channel:** Phone
- **Resolution Code:** Workaround provided
- **Resolution Notes:** Restarted VPN-SRV-02 service as per emergency change request

---

## Project Objective

The objective of this project is to automate and standardize the Incident Management lifecycle using ServiceNow's Incident module.

**Key objectives include:**

- Enable Service Desk agents to create and classify incidents efficiently
- Integrate Knowledge Management for faster resolution and self-service capabilities
- Allow reassignment to appropriate support groups and Level 2 teams
- Enable Level 2 technicians to investigate and resolve complex incidents
- Create emergency change requests directly from incidents
- Allow child incident creation for tracking recurring issues and dependencies
- Generate knowledge articles from resolved incidents to build organizational knowledge base
- Improve SLA compliance and provide service visibility to all stakeholders
- Establish multi-team collaboration workflow for better issue resolution

---

## Functional Scope

The project implements the following functional features:

1. **Incident Record Creation** in Service Operations Workspace
2. **Incident Classification**
   - Category and Subcategory selection
   - Urgency and Impact assessment
   - Service and Service Offering mapping
   - Configuration Item association
3. **Agent Assist Knowledge Integration** for contextual article suggestions
4. **Reassignment to Level 2 Support Teams** with automatic field clearing
5. **Emergency Change Request Creation** for required infrastructure changes
6. **Child Incident Creation** for tracking recurring or related issues
7. **Incident Cause and Resolution Documentation** with structured fields
8. **Knowledge Article Creation from Incident** for knowledge base building
9. **SLA and Related Record Tracking** for compliance monitoring

---

## Stakeholder Mapping

### 1. End Users
- **Role:** Report IT issues
- **Needs:** Quick resolution and visibility
- **Automation Impact:** Faster issue resolution and transparent tracking

### 2. Service Desk Agents
- **Role:** First-level support and incident intake
- **Needs:** Easy logging and classification tools
- **Automation Impact:** Standardized intake process and faster escalation to Level 2

### 3. Level 2 Support – Network/Hardware Teams
- **Role:** Diagnose and resolve complex technical issues
- **Needs:** Complete incident data and related records
- **Automation Impact:** Better diagnosis capability and clear task ownership

### 4. Change Management Team
- **Role:** Handle emergency changes and infrastructure updates
- **Needs:** Structured change requests with incident context
- **Automation Impact:** Integrated change control with incident dependencies

### 5. ServiceNow Admin
- **Role:** Maintain platform configuration and governance
- **Needs:** Scalable and trackable solution
- **Automation Impact:** Controlled process management and audit trail

---

## Project Milestones

The project is structured across the following milestones:

| # | Milestone | Description |
|---|-----------|-------------|
| 1 | Incident Record Creation | Initial incident logging in Service Operations Workspace |
| 2 | Incident Classification | Categorization, prioritization, and service mapping |
| 3 | Knowledge Integration | Agent Assist retrieval and knowledge article attachment |
| 4 | Reassignment & Escalation | Assignment to Level 2 Network support team |
| 5 | Change Request Creation | Emergency change for infrastructure modification |
| 6 | Child Incident Creation | Tracking VPN authentication failure as child incident |
| 7 | Incident Resolution | Documentation of cause, resolution code, and notes |
| 8 | Knowledge Creation | Automatic knowledge article generation for resolution |
| 9 | SLA & Related Record Validation | Final compliance and record verification |

---

## Technology / ServiceNow Features

**Platform:** ServiceNow (ITSM Module)

**Key Features Used:**

- Service Catalog and Service Offering configuration
- Incident Management module
- Agent Assist for Knowledge integration
- Change Management module
- Knowledge Management module
- SLA (Service Level Agreements) tracking
- Related Records and Child Incidents
- Work Notes and Watch List functionality
- Configuration Management Database (CMDB) integration
- Service Operations Workspace

---

## Service Configuration

### Service Configuration Steps

**Navigation:** All → cmdb_ci_service.LIST → New

**Service Details:**

| Field | Value |
|-------|-------|
| **Name** | Remote Access |
| **Operational Status** | Operational |
| **Description** | [TO BE ADDED] |

### Service Offering Configuration

**Navigation:** All → service_offering.LIST → New

**Service Offering Details:**

| Field | Value |
|-------|-------|
| **Name** | Corporate VPN |
| **Parent** | Remote Access |
| **Operational Status** | Operational |
| **Description** | [TO BE ADDED] |

**Configuration Notes:**
- Both Service and Service Offering are configured with "Operational" status
- Service Offering is linked to the Remote Access Service as parent
- These configurations enable incident classification with proper service hierarchy

---

## Incident Creation

### Workflow: Initial Incident Logging

**User Impersonation:** Beth Anglin

**Navigation Path:** Service Operations Workspace → List → Incidents → Open

**Steps:**

1. Click **New** button to create incident
2. Enter **Short Description:** Unable to connect to Corporate VPN from home office
3. Select **Caller:** Michael Hoefer
4. Click **Save**
5. Open **Details** tab
6. Initially assign incident to **Service Desk** group

**Incident Record Created:**
- **Incident Number:** INC0010001
- **State:** New (assigned to Service Desk)
- **Initial Assignment Group:** Service Desk

---

## Incident Classification

### Workflow: Incident Categorization and Assignment

**User Impersonation:** Beth Anglin (Service Desk Agent)

**Updates Applied:**

| Field | Value |
|-------|-------|
| **Description** | Michael advised he was able to connect yesterday evening, but this morning received an authentication error. The Internet works fine. |
| **Channel** | Phone |
| **Category** | Network |
| **Subcategory** | VPN |
| **Urgency** | 2 - Medium |
| **Impact** | 3 - Low |
| **Priority** | 4 - Low |
| **Service** | Remote Access |
| **Service Offering** | Corporate VPN |
| **Configuration Item** | ThinkStationS20 (or applicable available CI) |
| **Work Notes** | Classified and assigned incident. |

**Action:** Click **Assign to me**

**Outcome:**
- Incident properly classified with complete incident details
- Assigned to Service Desk agent for initial triage
- Ready for escalation to Level 2 if required

---

## Agent Assist and Knowledge Integration

### Workflow: Leveraging Knowledge Articles

**Agent Assist Panel Steps:**

1. Open the **Agent Assist** panel on the right-side of the incident form
2. Ensure **Knowledge Articles** are selected as the search type
3. Verify that knowledge articles appear based on the incident short description
4. Open a relevant knowledge article from the suggested list
5. Select the **three-dot menu** on the article
6. Mark Article as **Helpful**
7. Select **Attach Article**
8. Add **Comment:** "Follow the Steps and Resolve the Incident."
9. Click **Attach** to link the article

### Verification in Incident Record:

**Activity Log Should Show:**
- Knowledge article linked and attached
- Helpful indicator marked
- Agent's comment recorded

**Benefits:**
- Faster resolution through contextual knowledge
- Reduced resolution time (RFR)
- Better consistency in solutions
- Improved customer satisfaction

---

## Watch List and Work Notes

### Watch List Management

**Action:** Add **Samantha Bordwell** to the Watch list

- Watch list users receive notifications on incident updates
- Can monitor progress without direct assignment
- Enables oversight and quality assurance

### Work Notes List Management

**Action:** Add **Beth Anglin** to the Work notes list

- Work notes list users receive notifications when work notes are added
- Can review and track technical notes and updates
- Facilitates knowledge sharing across team

**Note:** If specified users are unavailable, available users may be substituted.

---

## Incident Reassignment

### Workflow: Escalation to Level 2 Support

**Assignment Update:**

| Field | Value |
|-------|-------|
| **Assignment Group** | Network |
| **Assigned To** | [Auto-cleared when group changes] |

**Steps:**

1. Update **Assignment Group** to Network
2. Verify **Assigned To** field automatically clears
3. Click **Save**

**Outcome:**
- Incident is now assigned to the Network support team
- Level 2 technicians can now access and claim the incident
- Proper escalation path established for technical investigation

---

## Level 2 Investigation

### Workflow: Technical Diagnosis and Resolution

**User Impersonation:** David Loo (Level 2 Network Support)

**Navigation:** Workspaces → Service Operations Workspace → Incidents → Open

**Steps:**

1. Open the VPN incident (INC0010001)
2. Click **Assign to me** to claim ownership
3. Review available information:
   - **Description:** Full incident description visible
   - **Knowledge Articles:** Attached articles visible for reference
   - **SLA Status:** View Task SLAs in Related Records section

**Verification Checklist:**

- ✓ Description clearly visible with all classification details
- ✓ Knowledge articles accessible for technical reference
- ✓ SLA timer visible under Task SLAs in Related Records
- ✓ Time tracking enabled for SLA compliance
- ✓ Parent incident context available
- ✓ Related records (change requests, child incidents) linked

**Level 2 Responsibility:**
- Analyze root cause of VPN connectivity issue
- Determine if change request or emergency action required
- Document findings in Cause field
- Coordinate with Change Management if needed

---

## Configuration Item Update

### Workflow: CMDB Modification

**Initial Configuration Item:** ThinkStationS20

**Updated Configuration Item:** PowerEdge

**Steps:**

1. Locate **Configuration Item** field in incident record
2. Change from **ThinkStation** to **PowerEdge**
3. Click **Save**

**Rationale:**
- PowerEdge is the actual affected infrastructure component
- Accurate CMDB association for asset tracking
- Proper Change Management correlation
- Better incident trend analysis by CI type

---

## Incident On Hold

### Workflow: Placing Incident on Hold

**Status Update:**

| Field | Value |
|-------|-------|
| **State** | On Hold |
| **On Hold Reason** | Awaiting Change |

**Steps:**

1. Update **State** to "On Hold"
2. Select **On Hold Reason:** Awaiting Change
3. Click **Save**

**Explanation:**
Incidents are placed on hold when:
- Waiting for emergency change request approval and implementation
- Awaiting third-party vendor response
- Pending resource availability or maintenance window
- Blocked by dependency on other incident resolution

**Benefits:**
- Prevents premature closure before prerequisite actions complete
- Maintains SLA tracking accuracy (hold time excluded from SLA)
- Provides visibility into blocked incidents
- Improves incident lifecycle transparency

---

## Child Incident Creation

### Workflow: Creating Related Incident

**Navigation:** Related Records → Child Incidents → New

**Child Incident Details:**

| Field | Value |
|-------|-------|
| **Short Description** | Unable to connect to Corporate VPN |
| **Caller** | [Any available user] |
| **Description** | User receiving VPN authentication failure error. |
| **Parent Incident** | INC0010001 |

**Steps:**

1. Navigate to **Related Records** section
2. Click **Child Incidents** section
3. Click **New** button
4. Enter child incident details
5. Click **Save**
6. Record the generated child incident number

**Verification:**

1. Return to parent incident (INC0010001)
2. Navigate to **Related Records** → **Child Incidents**
3. Verify child incident is listed and linked

**Use Case:**
- Child incidents track related issues (e.g., VPN authentication error)
- Maintains hierarchical relationship for better tracking
- Enables resolution of parent incident while child tracks follow-up action
- Improves incident metrics and trend analysis

---

## Cause Identification

### Workflow: Root Cause Analysis

**Cause Documentation:**

| Field | Value |
|-------|-------|
| **Probable Cause** | PowerEdge service was suspended and required restart. |

**Steps:**

1. Navigate to the **Cause** section in incident record
2. Enter **Probable Cause:** "PowerEdge service was suspended and required restart."
3. Click **Save**

**Investigation Findings:**
- Root cause identified: Service suspension on PowerEdge CI
- Required action: Service restart
- Dependencies: Emergency change request needed
- Impact scope: Corporate VPN connectivity

---

## Incident Resolution

### Workflow: Documenting and Closing Incident

**Resolution Documentation:**

| Field | Value |
|-------|-------|
| **Resolution Code** | Workaround provided |
| **Resolution Notes** | Restarted VPN-SRV-02 service as per emergency change request. |

**Steps:**

1. Navigate to **Resolution** section
2. Select **Resolution Code:** "Workaround provided"
3. Enter **Resolution Notes:** "Restarted VPN-SRV-02 service as per emergency change request."
4. Click **Save**
5. Click **Resolve** button
6. Confirm resolution closure

**Outcome:**
- Incident marked as **Resolved**
- Resolution details captured for knowledge base
- SLA timer stopped for compliance reporting
- Incident available for knowledge article creation
- Closure documented with change request reference

---

## Knowledge Article Creation

### Workflow: Building Knowledge Base

**Navigation:** Incident Actions → Create Knowledge

**Steps:**

1. Click **Create Knowledge** button from incident record
2. Select **Knowledge Base:** IT
3. Select **Article Template:** Standard
4. Review all pre-populated details (pulled from incident)
5. Click **Next**
6. Verify and customize article content if needed
7. Click **Save**
8. Return to **Parent Record**
9. Navigate to **Related Records** → **Created Knowledge**
10. Verify the Knowledge Article was created and linked

**Knowledge Article Purpose:**
- Captures VPN connectivity troubleshooting procedures
- Documents workaround and resolution steps
- Available for future similar incidents
- Reduces resolution time (RFR) for recurring issues
- Builds organizational IT knowledge base

---

## Final Validation

### Complete Incident Lifecycle Verification

**Parent Incident (INC0010001) Validation:**

✓ **State:** Resolved
✓ **Service:** Remote Access
✓ **Service Offering:** Corporate VPN
✓ **Configuration Item:** PowerEdge
✓ **Assignment Group:** Network
✓ **Assigned To:** David Loo
✓ **On Hold Reason:** Awaiting Change
✓ **Probable Cause:** PowerEdge service was suspended and required restart
✓ **Resolution Code:** Workaround provided
✓ **Resolution Notes:** Restarted VPN-SRV-02 service as per emergency change request

**Child Incident Validation:**

✓ **State:** Resolved
✓ **Short Description:** Unable to connect to Corporate VPN
✓ **Parent Incident Link:** INC0010001
✓ **Related Records:** Visible in parent incident

**Related Records Validation:**

✓ **Activity Log:** Shows resolution triggered by parent incident
✓ **Change Request:** Linked (emergency change for service restart)
✓ **Knowledge Article:** Created and linked in Related Records
✓ **Task SLAs:** Visible and tracked
✓ **Watch List:** Notifications sent to Samantha Bordwell
✓ **Work Notes:** Added and visible to Beth Anglin

**SLA Tracking:**

✓ **SLA Timer:** Active during incident lifecycle
✓ **On Hold Time:** Excluded from SLA calculation
✓ **Resolution Time:** Recorded for metrics
✓ **Compliance Status:** [TO BE ADDED]

---

## End-to-End Incident Lifecycle

### Complete Process Flow

```
Incident Creation (Beth Anglin)
    ↓
[INC0010001 - Unable to connect to Corporate VPN]
    ↓
Incident Classification
    ├─ Channel: Phone
    ├─ Category: Network
    ├─ Subcategory: VPN
    ├─ Urgency: 2 - Medium
    ├─ Service: Remote Access
    └─ Service Offering: Corporate VPN
    ↓
Agent Assist Integration
    ├─ Knowledge Articles Retrieved
    ├─ Article Marked as Helpful
    └─ Article Attached to Incident
    ↓
Assignment & Escalation
    ├─ Initial: Service Desk
    └─ Escalated: Network (Level 2)
    ↓
Level 2 Investigation (David Loo)
    ├─ Review Description & Knowledge
    ├─ Access SLA Status
    ├─ Update Configuration Item: PowerEdge
    └─ Identify Cause: Service Suspension
    ↓
On Hold Status
    └─ Awaiting Change: VPN-SRV-02 Restart
    ↓
Child Incident Creation
    └─ [Child INC#] - VPN Authentication Error
    ↓
Change Request Execution
    └─ Restarted VPN-SRV-02 Service
    ↓
Resolution Documentation
    ├─ Code: Workaround Provided
    ├─ Notes: Service Restart Executed
    └─ State: Resolved
    ↓
Knowledge Creation
    └─ IT Knowledge Base Article Created
    ↓
Final Validation
    ├─ Parent Resolved
    ├─ Child Resolved
    ├─ Knowledge Linked
    ├─ SLA Tracked
    └─ Audit Trail Complete
```

---

## Testing

### Test Case Coverage

| Test ID | Test Scenario | Steps | Expected Result | Actual Result | Status |
|---------|---------------|-------|-----------------|---------------|--------|
| TC01 | Service Creation | Navigate to cmdb_ci_service.LIST, Create Remote Access service | Service created with Operational status | [TO BE ADDED] | [TO BE ADDED] |
| TC02 | Service Offering Creation | Navigate to service_offering.LIST, Create Corporate VPN offering under Remote Access | Service Offering created and linked to parent service | [TO BE ADDED] | [TO BE ADDED] |
| TC03 | Incident Creation | Login as Beth Anglin, navigate to Service Operations Workspace, Create new incident with VPN short description | Incident INC0010001 created with initial Service Desk assignment | [TO BE ADDED] | [TO BE ADDED] |
| TC04 | Incident Classification | Update incident with classification details (Network/VPN category, urgency, service mapping) | All classification fields populated; Assigned to me executed | [TO BE ADDED] | [TO BE ADDED] |
| TC05 | Agent Assist | Open Agent Assist panel, verify knowledge articles appear for VPN keywords | Knowledge articles displayed based on incident keywords | [TO BE ADDED] | [TO BE ADDED] |
| TC06 | Knowledge Article Attachment | Mark article as helpful, attach article with comment | Article linked in Activity log with helpful indicator marked | [TO BE ADDED] | [TO BE ADDED] |
| TC07 | Assignment | Add Samantha Bordwell to Watch list, Beth Anglin to Work notes list, reassign to Network group | Assigned To field auto-cleared; Users added to respective lists | [TO BE ADDED] | [TO BE ADDED] |
| TC08 | Level 2 Investigation | Impersonate David Loo, open incident, assign to self, verify description and SLA | Description visible; Knowledge articles accessible; SLA displayed in Related Records | [TO BE ADDED] | [TO BE ADDED] |
| TC09 | Configuration Item Update | Update CI from ThinkStation to PowerEdge | CI field updated and saved with correct PowerEdge reference | [TO BE ADDED] | [TO BE ADDED] |
| TC10 | On Hold | Set incident state to On Hold with reason "Awaiting Change" | Incident placed on hold; SLA timer paused; Reason recorded | [TO BE ADDED] | [TO BE ADDED] |
| TC11 | Child Incident Creation | Navigate to Related Records, create child incident for VPN authentication | Child incident created and linked to parent INC0010001 | [TO BE ADDED] | [TO BE ADDED] |
| TC12 | Cause Documentation | Add probable cause: "PowerEdge service was suspended and required restart" | Cause field populated and saved | [TO BE ADDED] | [TO BE ADDED] |
| TC13 | Resolution | Set resolution code to "Workaround provided", add notes, click Resolve | Incident state changed to Resolved; Resolution details saved | [TO BE ADDED] | [TO BE ADDED] |
| TC14 | Knowledge Creation | Click Create Knowledge, select IT knowledge base and Standard template | Knowledge article generated from incident and linked in Related Records | [TO BE ADDED] | [TO BE ADDED] |
| TC15 | Final Validation | Verify parent resolved, child resolved, activity shows resolution trigger, change linked, knowledge created | All validation points confirmed; Incident lifecycle complete | [TO BE ADDED] | [TO BE ADDED] |
| TC16 | SLA Tracking | Monitor SLA timer throughout incident lifecycle | SLA visible in Related Records; Time calculated excluding hold period | [TO BE ADDED] | [TO BE ADDED] |

---

## Results

### Project Execution Summary

[TO BE ADDED]

**Metrics:**
- Incident Resolution Time: [TO BE ADDED]
- Time in On Hold Status: [TO BE ADDED]
- Knowledge Article Generated: Yes
- Child Incidents Created: [TO BE ADDED]
- SLA Compliance: [TO BE ADDED]

---

## Advantages

1. **Standardized Process** – Consistent incident handling across all Service Desk agents
2. **Faster Resolution** – Agent Assist provides immediate knowledge base access
3. **Improved Escalation** – Clear assignment workflow to Level 2 teams
4. **Change Integration** – Emergency changes linked to incidents for traceability
5. **Knowledge Building** – Automatic knowledge article creation from resolved incidents
6. **SLA Compliance** – Built-in SLA tracking with hold time exclusion
7. **Multi-Team Collaboration** – Watch list and work notes enable cross-team visibility
8. **Audit Trail** – Complete activity log for compliance and quality assurance
9. **Child Incident Tracking** – Related issues tracked hierarchically
10. **Self-Service Ready** – Knowledge articles enable faster future resolutions

---

## Limitations

1. **Manual Configuration** – Initial service and service offering setup requires manual entry
2. **Knowledge Dependency** – Effectiveness depends on knowledge base population
3. **User Training** – Agents must understand proper classification and escalation
4. **Change Lead Time** – Emergency changes may have approval delays
5. **System Integration** – Relies on CMDB accuracy for Configuration Item matching
6. **SLA Definition** – SLA calculations depend on proper configuration
7. **Knowledge Article Review** – Requires quality review before publishing
8. **Skill Gap** – Level 2 team expertise required for complex technical issues
9. **Communication** – Requires active communication between teams during escalation
10. **Data Cleanup** – Requires regular maintenance to remove obsolete incidents/articles

---

## Future Scope

1. **AI-Powered Agent Assist** – Enhanced ML-based article recommendations
2. **Automated Escalation** – Rules-based automatic escalation to Level 2
3. **Predictive Analytics** – Forecast incident volume and resource requirements
4. **Mobile App Integration** – Mobile incident management for field teams
5. **Customer Portal** – Self-service incident creation and tracking for end users
6. **Sentiment Analysis** – Monitor caller satisfaction and sentiment in notes
7. **Chatbot Integration** – Natural language processing for incident classification
8. **Advanced Reporting** – Custom dashboards for incident metrics and trends
9. **Integration with Monitoring** – Auto-create incidents from monitoring alerts
10. **Closed-Loop Feedback** – Customer satisfaction surveys linked to incidents

---

## Conclusion

This project demonstrates a **complete Incident Management lifecycle automation** in ServiceNow, showcasing enterprise-grade ITSM practices.

**Key Achievements:**

Service Desk agents can log and classify incidents efficiently, leverage Agent Assist and knowledge base for faster resolution, escalate complex issues to Level 2 teams with complete context, initiate emergency change requests directly from incidents, and document final resolution with cause analysis and knowledge articles.

**Integration Benefits:**

The integration between Incident, Change, and Knowledge modules ensures:
- **Structured issue management** with standardized workflows
- **Improved SLA adherence** with accurate time tracking
- **Better IT service delivery** through knowledge base building
- **Multi-team collaboration** with clear responsibilities and visibility
- **Audit compliance** with complete activity trails
- **Continuous improvement** through knowledge creation from resolutions

**Project Validation:**

The scenario successfully validates:
- ✓ Complete incident lifecycle from creation to resolution
- ✓ Escalation process with level-based assignment
- ✓ Change integration with emergency change linking
- ✓ Knowledge creation for organizational learning
- ✓ Child incident management for related issue tracking
- ✓ SLA tracking with compliance monitoring
- ✓ Multi-team collaboration and communication
- ✓ Activity audit trail for compliance

This automation framework provides a scalable foundation for enterprise incident management, enabling better service quality, faster resolution times, and improved organizational efficiency.

---

## Screenshots

Screenshots documenting each phase of the incident lifecycle are organized in the `/Screenshots` directory by process step.

### Directory Structure:
- **01-Service-Configuration/** – Service and Service Offering setup
- **02-Incident-Creation/** – Initial incident logging
- **03-Incident-Classification/** – Incident categorization and assignment
- **04-Agent-Assist/** – Knowledge article retrieval
- **05-Knowledge-Integration/** – Article attachment and linking
- **06-Assignment-Reassignment/** – Escalation to Level 2
- **07-Level-2-Investigation/** – Technical diagnosis workflow
- **08-Configuration-Item/** – CMDB update process
- **09-On-Hold/** – On Hold status documentation
- **10-Child-Incident/** – Child incident creation
- **11-Cause/** – Root cause analysis documentation
- **12-Resolution/** – Resolution code and notes entry
- **13-Knowledge-Creation/** – Knowledge article generation
- **14-Final-Validation/** – Complete lifecycle verification

---

## Project Documentation

Comprehensive project documentation is available in the `/Documentation` folder:

- **Project-Report.pdf** – Complete project report with methodology, findings, and conclusions

---

## Project Demo

Project demonstration: [ADD SCREEN RECORDING LINK HERE]

---

## Repository Structure

```
servicenow-incident-lifecycle-automation/
├── README.md                          # Project documentation (this file)
├── Documentation/
│   └── Project-Report.pdf             # Comprehensive project report
├── Screenshots/
│   ├── 01-Service-Configuration/      # Service setup screenshots
│   ├── 02-Incident-Creation/          # Incident creation screenshots
│   ├── 03-Incident-Classification/    # Classification screenshots
│   ├── 04-Agent-Assist/               # Agent Assist screenshots
│   ├── 05-Knowledge-Integration/      # Knowledge integration screenshots
│   ├── 06-Assignment-Reassignment/    # Assignment screenshots
│   ├── 07-Level-2-Investigation/      # Level 2 investigation screenshots
│   ├── 08-Configuration-Item/         # Configuration Item update screenshots
│   ├── 09-On-Hold/                    # On Hold status screenshots
│   ├── 10-Child-Incident/             # Child incident screenshots
│   ├── 11-Cause/                      # Cause documentation screenshots
│   ├── 12-Resolution/                 # Resolution screenshots
│   ├── 13-Knowledge-Creation/         # Knowledge creation screenshots
│   └── 14-Final-Validation/           # Final validation screenshots
├── Diagrams/
│   ├── Stakeholder-Mapping/           # [DIAGRAM TO BE ADDED]
│   ├── Incident-Lifecycle/            # [DIAGRAM TO BE ADDED]
│   ├── Data-Flow/                     # [DIAGRAM TO BE ADDED]
│   └── Solution-Architecture/         # [DIAGRAM TO BE ADDED]
├── Testing/
│   ├── Test-Cases/
│   │   └── Test-Cases.md              # Test case documentation
│   └── Test-Results/
│       └── Test-Results.md            # Test execution results
└── Demo/
    └── demo-link.txt                  # Screen recording link
```

---

**Project Status:** Complete  
**Last Updated:** [TO BE ADDED]  
**Repository:** servicenow-incident-lifecycle-automation  
**Student:** Manasa Karri  
**College:** ISTS Women's Engineering College
