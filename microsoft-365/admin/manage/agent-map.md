---
title: Use Agent Map in the Microsoft 365 admin center
description: Learn how to use Agent Map to visualize, manage, and take action on agents in your Microsoft 365 tenant.
ms.date: 04/07/2026
author: erikre
ms.topic: concept-article
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
ms.reviewer: jenniferge
ms.author: erikre
manager: scotv
ms.service: microsoft-365-copilot
---
 
# Use Agent Map in the Microsoft 365 admin center 

Agent Map in the Microsoft 365 admin center gives IT and AI admins a visual way to understand and manage the agents running in their tenant. Instead of relying only on list-based views, Agent Map groups agents by the platform they were created on, making it easier to interpret large agent estates and spot adoption patterns at a glance.

Use Agent Map to explore your organization’s agent landscape, filter to specific subsets (such as ownerless agents), and drill into individual agents to review key details like ownership, configuration, and activity. You can also view how agents relate to each other, helping you understand dependencies and interactions as your agent footprint grows.

:::image type="content" source="../../media/agents/agent-map.png" alt-text="Screenshot showing the Agent Map, which provides an inventory of agents in the Microsoft 365 admin center." lightbox="../../media/agents/agent-map.png":::

You can use the Agent Map to focus on what needs your attention, rather than only on inventory details. Use the Agent Map to do the following:

- Spot patterns fast by identifying clusters of agents across your tenant.
- Slice the map with built-in filters to focus on the agents that matter right now. Filter by Status, Publisher type, Platform, Channel, or Usage.

  > [!NOTE]
  > Usage is supported through Agent 365 observability data for tenants with fewer than 4,000 agents.

- Track key signals at a glance with high-level metrics and agent-level indicators.
- Drill into any agent to review important details such as publisher, type, platform, version, and connectivity.

The Map complements the Registry by offering a more visual and scalable solution for environments with large numbers of agents. 
 
## View Agent Map

Use the following steps to view the Agent Map:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. In the left navigation pane, select **Agents** > **All Agents** > **Map**.

When you select the **Map** tab, the map loads agents from your tenant and displays them as icons grouped by platform and other metrics.

Agent Map is available to all Microsoft 365 Copilot administrators with an E7 (Agent 365) license. To access the Agent Map, your role must be either a **Global Administrator** or an **AI Administrator**. For more information about agent management roles, see [Agent management roles and permissions](agent-roles-perms.md).

### Clustering
 
By default, Agent Map clusters agents by the platform or by the builder the group of agents were created by. Each cluster appears as its own group on the map, so you can quickly view how agents are distributed across your environment.
 
| Cluster | What agents appear here |
|---|---|
| **Microsoft 365 Copilot Agent Builder** | Agents built using the Microsoft 365 Copilot Agent Builder tool |
| **Copilot Studio** | Agents built using Microsoft Copilot Studio |
| **Copilot Studio Legacy** | Agents built using an earlier version of Copilot Studio |
| **Microsoft 365 Agents Toolkit** | Agents built using the Microsoft 365 Agents Toolkit (formerly Teams Toolkit) |
| **SharePoint** | Agents built using SharePoint |
| **Azure AI Foundry** | Agents built using Azure AI Foundry |
| **Amazon Bedrock** | Agents built using Amazon Bedrock |
| **Google Vertex AI** | Agents built using Google Vertex AI |
| **Microsoft** | First-party agents built and maintained by Microsoft |
| **External Partners** | Third-party agents from external publishers not associated with a known builder |
| **Others** | Any agents that don't match a known platform or publisher |
 
### Searching and filtering agents
 
You can find specific agents quickly by name, using the **search bar** at the top of Agent Map. You can also refine what you’re looking at with **filters** that reshape the map around what matters.

The agent summary details, which are provided as cards at the top of the pane, can be selected to provide a mutual exclusive summary. However, the dropdown filter selections, below the cards, can be combined independently.  

Available quick filters include the following:

- **Agents at risk** - Show only agents with one or more active security risks. The count shown reflects high-severity alerts sourced from Microsoft Entra.
- **Agents without owners** - Show shared agents that no longer have an active owner, such as agents whose creator has left the organization.
- **Blocked agents** - Show only agents that are currently blocked across your organization.

The following table provides filter details:

| Filter group | Filters | Description |
|---|---|---|
| **Status** | Available<br>Blocked<br>Draft<br>Not activated | Narrows the view by how widely an agent is currently available in your tenant. This view can show a limited rollout to a fully blocked or unavailable view. |
| **Publisher type** | Your org<br>Your users<br>Microsoft<br>Third party | Lets you slice the map by who published or distributed the agent, allowing you to separate first-party, third-party, and internally produced agents (including creator-shared agents). |
| **Platform** | Copilot Studio<br>Agent Builder in Microsoft 365 Copilot<br>Microsoft Foundry<br>SharePoint<br>Microsoft 365 Agents Toolkit<br>Amazon Bedrock<br>Other | Groups agents by the platform they were built on to help you understand build provenance, tooling trends, and governance coverage across your estate. |
| **Channel** | Copilot<br>Outlook<br>Teams<br>Microsoft 365 apps<br>SharePoint | Filters agents by where users encounter them, so you can investigate exposure and adoption by host product. |
| **Usage** | Active users (30D): Top 100 by users, Inactive<br><br>Total sessions (30D): Top 100 by sessions, No sessions<br><br>Exception rate (30D): Has exceptions (>0%), No exceptions<br><br>Assisted hours (30D): Has assisted hours, No assisted hours<br><br>Security: Has security alerts | Highlights agents by recent usage and reliability and security signals so you can prioritize high-impact agents, find unused ones, and spot agents that may need attention. |

> [!NOTE]
> For performance reasons, the Usage filters are currently available only for tenants with fewer than 4,000 agents. Usage is based on agents reporting activity via Agent 365.

### Exporting agents
 
You can export the full list of agents displayed in the Agent Map to an Excel file. Select **Export** to download agent details for reporting, auditing, or compliance purposes.
 
## Interface features

The Agent Map provides controls to help you navigate the map.

- **Zoom In/Out**: Adjust the map view for closer inspection or broader visualization.
- **Keyboard shortcuts**: Provides a key to **Keyboard shortcuts**. You can select this option to see navigation, zoom, selection and general keyboard shortcuts.
- **Settings**: Provides a slider to control the **Max agents per platform** in the Agent Map. 
 
## Agent details
 
When you select an icon for a specific agent, you can see more details about the agent, including:
 
- Details:
  - Description
  - Publisher
  - Agent type
  - Platform
  - Last updated
  - Version
- Users
- Data and tools
- Security
- Activity

For more information about agent details, see [Understand agent details in Microsoft 365 admin center](agent-details.md). 
 
## Taking action on agents
 
From the Agent Map, you can take administrative actions directly on agents without leaving the map view. When you select an agent, the details pane opens and provides available actions based on the agent's current state.
 
Available actions are based on the state of the agent. The action can include the following:
 
- **Assign owner** – Assign an owner to an agent that currently has no active owner. You can only assign ownership to users with a Copilot license.
- **Block** – Blocks the agent from members of your organization. They won't be able to install or use the agent. Additionally, the agent will be removed from any member of your organization who has already installed it.
- **Unblock** – Restore access to a previously blocked agent.
- **Install** - Deploys and installs the agent to the selected users.
- **Pin for users** - The agent will be pinned in the UI (based on channel) where the agent was deployed, so that the agent can be found more easily. Based on the users or groups where the agent was deployed, you can specify who will have the agent pinned.

These actions are reflected in both the Agent Map and the Registry tab. For a full list of available admin actions, see [Agent Registry in the Microsoft 365 admin center](agent-registry.md).
