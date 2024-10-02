# LeanTimeReporting
**Overview**

Lean Time Reporting (LTR) is a streamlined approach for Agile teams to track time, replacing traditional time tracking tools and processes.

**Introduction**

Traditional time tracking requires users to enter the number of hours spent on different tasks, projects, and clients. To be accurate, the timesheets need to be completed at least once a week, or even every day to ensure good accuracy. Indeed, studies are showing that reporting time at the end of the month decreases the accuracy to 40% according to the Ebbinghaus Forgetting Curve. The issue is that time tracking is often perceived as time consuming, nonvalue added, and too granular. It is thus not the priority of users. Furthermore, some users might be required to track their activities in a different system than their day-to-day Application Lifecycle Management tool. 

The goal of the Lean Time Reporting is to prevent manual entries per tasks on a timesheet (most common method), usage of timer to clock time while working on tasks, or calculation of the elapsed time spent in one status per assignee and per task. The last two methods require up -front assignment of the tasks and continuous updates of these assignments in case of priorities or availability changes.

Lean Time Reporting not only allows users to focus on the execution of their tasks and transfer the management of the reporting of time spent to the Release Train Engineers (SAFe Methodology), but also allows to report time at a granular level (up to the user story) without complexifying the process. This prevents some projects/teams from compromising the granularity of information collected to ensure accurate time spent. Furthermore, as Lean Time Reporting requires strong Agile practices, it pushes the team towards continuous improvement, it is an incentive to adopt the agile mindset.

**Definitions**


|Terms            | Definitions                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------|
| WBS (Work Breakdown Structure) |SAP WBS (Work Breakdown Structure) refers to the model of the project that organizes project tasks into a priority list and outlines a hierarchical list for each task. An individual WBS element represents specific activities within the overall work breakdown structure.|
|Team dedication |The Team Dedication reflects how much time and effort a team member devotes to the goals and deliverables of the team. In our system it is a percentage. Someone who has no work to be done outside his/her team is fully dedicated to the team (100% of dedication) |
|WBS lowest element |Can be the user story or the feature (SAFe methodology) |

Model principles and considerations
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

