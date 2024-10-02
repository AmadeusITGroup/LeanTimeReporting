# LeanTimeReporting
## Overview

Lean Time Reporting (LTR) is a streamlined approach for Agile teams to track time, replacing traditional time tracking tools and processes.

## Introduction

Traditional time tracking requires users to enter the number of hours spent on different tasks, projects, and clients. To be accurate, the timesheets need to be completed at least once a week, or even every day to ensure good accuracy. Indeed, studies are showing that reporting time at the end of the month decreases the accuracy to 40% according to the Ebbinghaus Forgetting Curve. The issue is that time tracking is often perceived as time consuming, nonvalue added, and too granular. It is thus not the priority of users. Furthermore, some users might be required to track their activities in a different system than their day-to-day Application Lifecycle Management tool. 

The goal of the Lean Time Reporting is to prevent manual entries per tasks on a timesheet (most common method), usage of timer to clock time while working on tasks, or calculation of the elapsed time spent in one status per assignee and per task. The last two methods require up -front assignment of the tasks and continuous updates of these assignments in case of priorities or availability changes.

Lean Time Reporting not only allows users to focus on the execution of their tasks and transfer the management of the reporting of time spent to the Release Train Engineers (SAFe Methodology), but also allows to report time at a granular level (up to the user story) without complexifying the process. This prevents some projects/teams from compromising the granularity of information collected to ensure accurate time spent. Furthermore, as Lean Time Reporting requires strong Agile practices, it pushes the team towards continuous improvement, it is an incentive to adopt the agile mindset.

## Definitions


|Terms            | Definitions                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------|
| WBS (Work Breakdown Structure) |SAP WBS (Work Breakdown Structure) refers to the model of the project that organizes project tasks into a priority list and outlines a hierarchical list for each task. An individual WBS element represents specific activities within the overall work breakdown structure.|
|Team dedication |The Team Dedication reflects how much time and effort a team member devotes to the goals and deliverables of the team. In our system it is a percentage. Someone who has no work to be done outside his/her team is fully dedicated to the team (100% of dedication) |
|WBS lowest element |Can be the user story or the feature (SAFe methodology) |

## Model principles and considerations
1.	Lean time reporting works at team level, and it differentiates the different roles of a team (Scrum Master, Developers, etc)
    - Note that it cannot track the time of a specific individual.
    - The calculation will take into consideration the deliveries made by the team and the capacity for all the team members.
2.	Lean time reporting relies on 2 main sources of information, the capacity of the team for a given period on one side, and the number of points delivered during this period on the other side.
    - The team's capacity can be defined in hours or number days; in the case presented here, the cost on the WBS will be collected in Effort Days.
    - The unit to estimate the overall effort required to fully implement a product backlog item or any other piece of work is the Story Points but can be any other unit of measure.
3.	As team members might not be 100% dedicated to the team, lean time reporting requires capturing the capacity of one team member taking into consideration the absences, and any other tasks performed outside the team. 
    - Lean time reporting uses the time tracking tool to capture the capacity.
    - It allows hybrid time tracking methods.
4.	Ideally, the period to consider should be an Agile sprint.
    -	As some time tracking tools and financial systems might run on a weekly or monthly basis, experience has shown that over the fiscal year, the impact of not being aligned with the Agile sprint duration is minimal.
5.	Lean time reporting extracts the data from different systems (that can be grouped in one system), the application lifecycle management tool and the time tracking tool; it pushes the information to the financial project management system. It allows full flexibility in terms of deployment and requires no specific on the shelf applications.
6.	Lean time reporting can be fully automated if the capacity of the team is accurate and if team members are 100% dedicated to the team, timecards are no longer completely by any team members.
7.	In the case of SAFe Agile Release trains, lean time reporting allows the Release Train Engineer, the Product Manager, the System Architect and potentially some shared services (experts, UX designers, …) helping the other teams of the train to allocate their capacity to all the deliveries of the train, simplifying their time tracking activities.
8.	Lean time reporting can work either if the team is a scrum team or is using kanban.
9.	Lean time reporting is described here in the Agile context, but it can be used in other contexts such as support teams where the allocation keys can be for example the number of tickets (volumetric KPI) instead of story points.

### Details

In the description below, the lean time reporting runs on 3 different applications:
-	The capacity tracking tool is SAP CATS to track the capacity of the team for the period and to remove any unproductive days (absences, weekends…). It is also used to track time spent in a traditional manner if some tasks are performed outside the context of the Agile team. The capacity of the team is then adjusted automatically and reflects the reality. 
-	The financial project management system is also SAP. The costs collected through time tracking, purchase orders receipts, etc are posted on the WBS maintained in SAP. 
-	The application lifecycle tool is Jira. Jira is used to describe the detailed activities of the WBS thus each relevant Jira ticket has a link to the SAP WBS lowest level.

  To simplify the explanations below, the SAP WBS lowest level will be a feature taking assumption that the link is made at this level between Jira Epic (SAFe Feature) and the WBS. It refers below to a WBS_Feature.

  ![ ](/assets/figure1.png)
1.	A first data integration is required to ensure that the activities, Jira epics in this example, are linked to the financial project management system WBS. It is the responsibility of the Release Train Engineer to ensure it is done. 
-	Option 1:  Jira stores the information of the WBS in its tickets
-	Option 2: SAP WBS stores the information of the ticket. 
Both options have been used. The decision has been made to be at Jira Epic level (SAFe Feature) to not over complexify the WBS. Still, it remains feasible and has been experienced to be at user story level.
2.	A second data integration is required to ensure that the team, the team members, their roles (if required), and their team dedication (one person might not work 100% for one team and may be part of several teams, working thus on different backlog of activities) are shared between the time tracking tool and the application lifecycle tool (Jira).
This allows the automation of the completion of the timecards (lean timesheet filling) if required
3.	A third data integration is used to import in the financial project management system (SAP) the user story points per Feature. Note as both the time tracking tool and the financial project management system are in SAP, the transfer of the capacity of each team to the project financial system is done using standard SAP transaction.
A dashboard can be used for the Release Train Engineer (RTE) to monitor the user story points per WBS_Feature, and simulate the reallocation of the time spent (effort days) to the WBS if needed.
This dashboard can be used to request the RTE to validate the simulation before the finance system performs the reallocation. It can be auditable evidence (capitalization processes) that the hours collected are accurate and representative of what has been created and the effort to create them.

### Reallocation of the effort days to the WBS in the financial project management system. 

 ![ ](/assets/figure2.png)  

The data is retrieved every month as requested by the financial policy of the company.
1.	The capacity is retrieved in hours and is converted to Effort-Days based on the company policy that 1 Effort-day is 8 hours. 
2.	For each team, a total capacity is defined per month based on the team dedication. Note that a team member can adjust the contribution to the team's capacity. For example, if the team member is dedicated to 2 teams and has worked exceptionally solely for one team, the timecard can be adjusted. If the team member is also on other activities not managed in Agile, the timecard can be used to report at the same time, the team capacity and the time spent on traditional activities.
3.	The system calculates the cost per story point for each team by dividing the Team Capacity retrieved for the month by the number of story points delivered by the team during that period of time.
  
![ ](/assets/Calc1.png)

For each WBS_Feature, the effort day are then calculated as follows:

![ ](/assets/Calc2.png)

### Additional calculation:
In an Agile Release Train, there are some members playing a transversal role, for example the Release Train Engineer. 

The lean time reporting proposes regrouping them in a transversal team. The time spent by each member of this team is recorded against this team. As this team does not really deliver story points per say, lean time reporting uses the results of the previous method.
For each WBS_feature, the system sums the number of Effort Days required by all the teams of Agile Release Train. It is then proportionally dispatching the capacity of each team member to the WBS_feature based on this.

### Notion of CAPEX and OPEX
As per SAFe recommendations, https://v5.scaledagileframework.com/capex-and-opex/, some features are Capex potential and some other tickets (like Maintenance tickets) are not. Jira can send the points aggregated at WBS_feature level in two categories, Capex potential or non-capex.

The effort days for each WBS_feature is then split in the financial project management system into 2 different activity types. Depending on other capitalization rules, the CAPEX time spent might be capitalized at the end.

In this example, each team member has a role defined (Scrum Master, Product Owner, Developer, etc…). the notion of CAPEX potential can be overwritten if by company capitalization rules some roles cannot be considered as delivering potentially capitalizable activities as they are considered as being part of the Requirements/design phases.




