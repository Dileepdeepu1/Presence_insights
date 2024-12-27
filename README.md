###Introduction

In this project, I created a Power BI dashboard for a company using an employee presence dataset. After gathering requirements, I cleaned, analyzed, and visualized the data to provide actionable insights, offering a clear overview of employee presence.

###In this I have used DAX for creating matrix in PowerBI

 1)Attendace % = DIVIDE([Present Days],[Office Working days],0)
2)Count = COUNT('Final Data'[Value])
3)HFWH Count = CALCULATE([Count],'Final Data'[Value]="HWFH")
4)Office Working days = 
Var totaldays = [Count]

VAR nonworkdays = CALCULATE([Count],'Final Data'[Value] in {"HO", "WO"})

RETURN
totaldays-nonworkdays
5)Present Days = CALCULATE([Count],'Final Data'[Value] in {"P", "WFH"}) 
6)SL % = DIVIDE('Measures (2)'[SL Count], [Office Working days])
7)SL Count = SUM('Final Data'[SL Count])
8)WFH % = DIVIDE([WFH Count],'Measures (2)'[Present Days],0)
9)WFH Count = SUM('Final Data'[WFH Count])

###End result

This project was a comprehensive Power BI dashboard that effectively visualized employee presence data. It provided actionable insights through interactive visualizations, helping the company make data-driven decisions to optimize workforce management and improve operational efficiency.
