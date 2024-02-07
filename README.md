# SQL-Murder-Mystery
There's been a Murder in SQL City! The SQL Murder Mystery is designed to be both a self-directed lesson to learn SQL concepts and commands and a fun game for experienced SQL users to solve an intriguing crime.

## Website
**🌐Knight Lab**
- [knightlab.com](https://mystery.knightlab.com/)

## Walkthrough for solve the Murder Mystery with SQL

A crime has taken place and the detective needs your help. The detective gave you the crime scene report, but you somehow lost it. You vaguely remember that the crime was a ​murder​ that occurred sometime on ​Jan.15, 2018​ and that it took place in ​SQL City​. Start by retrieving the corresponding crime scene report from the police department’s database.

All the clues to this mystery are buried in a huge database, and you need to use SQL to navigate through this vast network of information. Your first step to solving the mystery is to retrieve the corresponding crime scene report from the police department’s database. Below we'll explain from a high level the commands you need to know; whenever you are ready, you can start adapting the examples to create your own SQL commands in search of clues -- you can run any SQL in any of the code boxes, no matter what was in the box when you started.

## Relational Schema Diagram
*A schema diagram is a visual representation of structured data, illustrating how each element interacts and relates with others.*

Here is the schema for our database:

<img align="center" alt="Schema" width="500" src="https://github.com/Harshitha129/SQL-Murder-Mystery/assets/89914609/fe6d389e-a50a-42fc-8e35-6ee36067ccab">


## Tasks I sloved

**Task**: 
<p>Established a connection to the police department's database in Python.</p>
<p>In this mystery they have provided me the database file I need to connect that in Python.</p>

- If you want to connect the database that they've given, I'll give you a Hint (Hint: **import sqlite3** ). Ensure that you can access the necessary tables for the investigation.

```
#importing sqlite3
import sqlite3 as sql
```

#### 🔎Retrieve Crime Scene Report:
- **Task**: Run a query to retrieve the crime scene report for the murder that occurred on Jan.15, 2018, in SQL City. Gather all available details from the report.
```
query_1 = """
SELECT *
FROM crime_scene_report
WHERE city = 'SQL City'
ORDER BY date;
"""
pd.set_option('display.max_colwidth', None)
pd.read_sql_query(query_1, con)
```
#### 🔎Witness Personal Details:
- **Task**: Check the personal details of witnesses involved in the case. Retrieve their names, addresses, and any other relevant information.
#### 🔎View Witness Interviews:
- **Task**: Access the recorded interviews of witnesses conducted after the murder. Gather insights into their statements and potential clues.
#### 🔎Check Gym Database:
- **Task**: Investigate the gym database using details obtained from the crime scene report and witness interviews. Look for any gym-related information that might be relevant.
#### 🔎Check Car Details:
- **Task**: Examine the car details associated with the crime scene. Retrieve information about the vehicles present during the incident.
```
query_6 = """
SELECT *
FROM drivers_license
WHERE plate_number like "%H42W%";
"""
pd.read_sql_query(query_6, con)
```
#### 🔎Personal Details:
- **Task**: Identify and collect personal details mentioned in the previous query. This includes names, addresses, and any additional details.
#### 🔎Membership Status at the Gym:
- **Task**: Determine who is identified in the previous query as a member of the gym. Utilize the gym database to confirm their membership status.
#### 🔎Analyze and Draw Conclusions:
- **Task**: Analyze the collected data, including crime scene reports, witness interviews, gym records, and car details. Draw conclusions or hypotheses based on the information available.
#### 🔎Document Findings:
- **Task**: Document your findings and any insights gained from the SQL investigation. Summarize the key details that lead you to your conclusions.
#### 🔎Prepare a Report:
- **Task**: Prepare a detailed report for the detective, summarizing the events, suspects, and your conclusions. Present the evidence and rationale behind your findings.
#### 🔎Reflect on the Investigation:
- **Task**: Reflect on the investigative process. What challenges did you encounter, and how did you overcome them? Share your reflections on the case-solving experience.
```
query_12 ="""
SELECT person_id, count(*), event_name
FROM facebook_event_checkin
GROUP BY person_id
having count(*) = 3 AND event_name = "SQL Symphony Concert" AND date like "%201712%";
"""
pd.read_sql_query(query_12, con)
```

This approach turns the investigative process into actionable tasks, encouraging me to explore the database, extract relevant information, and piece together the clues to solve the SQL Murder Mystery. 


## End Result

<img align="center" alt="Result" width="600" src="https://github.com/Harshitha129/SQL-Murder-Mystery/assets/89914609/0ada0f34-9050-435e-bf8c-22e5d89d81f9">

## Credits 
The SQL Murder Mystery was created by **Joon Park** and **Cathy He** while they were Knight Lab fellows.


<h3 align="center">✨Good Luck Detective🦸‍♀️💫</h3>
