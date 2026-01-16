# Power Automate Flow – Remove Agents from Default Environment

## Overview

Currently, **there is no native option** in the Power Platform to prevent users from creating **Agents** in their **Default environment**.
For organizations with governance requirements, this flow provides a **workaround** by automatically deleting Agents created in that environment.

This repository shares a **Power Automate Flow** that removes Agents from a specified environment and notifies administrators of the actions taken.

---

## Purpose of the Flow

The goal of this flow is to:

- Automatically remove Agents created in the **Default environment**
- Enforce governance policies consistently
- Reduce manual administrative effort
- Provide visibility to administrators through email notifications

This flow is provided as a **reference implementation** and can be customized as needed.

---

## How the Flow Works

The flow follows these steps:

1. **Retrieve Agents**
   - Pull information for all existing **Agents** in a specific environment (for example, the Default environment).

2. **Store Agent Data**
   - Store all retrieved Agent information in a **variable** for processing and reporting.

3. **Delete Agents**
   - Loop through each Agent and delete it using the Dataverse action:
     **Perform a bound action in selected environment**
   - Action name used:
     ```
     PvaDeleteBot
     ```

4. **Generate Audit Report**
   - Create an **HTML table** containing details of the deleted Agents.

5. **Notify Administrators**
   - Send an **email notification** to administrators with the HTML table attached or embedded, providing visibility into which Agents were deleted.

---

## Trigger Configuration

- The current flow trigger is **Manual**
- You can change it to a **Scheduled (Recurrence)** trigger and run it:
  - Daily
  - Weekly
  - Or at any frequency required by your governance policy

> 💡 **Recommendation:** A scheduled trigger ensures continuous enforcement without manual intervention.

---

## User Communication (Strongly Recommended)

Because users can still create Agents in the Default environment, it is important to **inform makers** in advance.

### Maker Welcome Message

You can configure a **Maker welcome message** in a **Managed Environment**:

1. Go to **Power Platform Admin Center**
2. Navigate to
   **Manage → Environments → Select Environment → Edit Managed Environments**
3. Locate the **Maker welcome content** section
4. Add a message explaining:
   - Agents should not be created in the Default environment
   - Agents created there will be automatically deleted
   - Which environment should be used instead

The welcome message supports:
- **Markdown formatting**
- **Links** to internal documentation or governance guidance

---

## Official Documentation

For more information about Maker welcome content, see:

🔗 https://learn.microsoft.com/en-us/power-platform/admin/welcome-content?WT.mc_id=ppac_inproduct_env

---

## Disclaimer

- This solution is a **workaround**, not a native platform feature
- The flow is provided **as-is**
- Always test in a **non-production environment**
- Review permissions and deletion logic carefully before enabling automation

---

## License

Add your license information here (for example, MIT License), or remove this section if not applicable.
