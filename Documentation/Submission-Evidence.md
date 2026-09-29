# Submission Evidence – ServiceNow Incident Lifecycle Automation

**Student:** Manasa Karri  
**Environment:** SkillWallet → ServiceNow  
**Primary Incident:** INC0010001 – Unable to connect to Corporate VPN from home office

## Latest Evidence Captured

The latest ServiceNow evidence covers the following workflow states and actions:

1. **Network assignment** – Incident assigned to the Network group; Agent Assist and related records visible.
2. **Incident overview** – INC0010001 overview with caller, description, priority, impact and urgency.
3. **On Hold** – State changed to **On Hold** with **Awaiting Change** as the hold reason.
4. **Network reassignment** – Assignment Group = Network and Assigned To = David Loo.
5. **Parent/child relationship** – Related Records shows the parent incident reference to INC0010002.
6. **Cause documentation** – Probable Cause recorded as: `PowerEdge service was suspended and required restart.`
7. **Resolution section** – Resolution details prepared for closure.
8. **Resolve dialog** – Resolution Code = **Workaround provided** and Resolution Notes = `Restarted VPN-SRV-02 service as per emergency change request.`

## Expected Screenshot Mapping

| Evidence | Recommended file name |
|---|---|
| Network assignment / Agent Assist | `08-network-reassignment.png` |
| Incident overview | `09-level2-investigation.png` |
| On Hold / Awaiting Change | `11-on-hold-awaiting-change.png` |
| Parent-child incident | `12-child-incident.png` |
| Cause | `13-cause.png` |
| Resolution | `14-resolution.png` |
| Resolve confirmation | `15-resolve-dialog.png` |

## Important

Do not upload credentials, passwords, tokens, private account information, or unrelated screenshots. Keep the original ServiceNow screenshots as PNG/JPG evidence in the `screenshots/` folder.
