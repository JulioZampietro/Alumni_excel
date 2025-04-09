# Analysis of the Trajectories of Alumni from a Top-Ranking Brazilian University

### Summary
Using two tables (Alumni and Activities), which contain data collected from 2005 to 2023 on over 600 alumni from a top-ranking History graduate program in Brazil, I was able to compile data on the professional trajectories of over 450 of them. Among the potential conclusions, four warranted greater attention and are summarized in the Dashboard. First, the vast majority of alumni attained teaching or research roles. Second, alumni often did not stray too far from the University's state, as little over 25% of them effectively left their state's region. Third, from those alumni who pursued a teaching career, over half of them attained positions as higher education professors, which helps to attest the quality of the graduate program. And lastly, while alumni who attained a PhD represent the majority of those in teaching roles, terminal MA holders represent the vast majority of those who pursued a career in the private sector.


### Data cleaning and manipulation: step by step
1. Filtered the original tables for History students & removed duplicates, which represented those that attained both an MA and a PhD from the same institution.
2. Removed sensitive information (full names became tags, and the e-mail, telephone, salaries, gender, and race columns were removed from the Alumni table).
3. Used conditional formatting to find those in the Activities table that had more than one activity assigned to them, either because of outdated data or human error. Rectified this for each case, also assigning their proper activity in the Activity column.
4. Cleaned data in the Activities table (converged equivalent terms such as USA and United States of America; cleared null values that should not be null; typo adjustments).
5. Translated all relevant data into English.
6. Used VLOOKUP functions to transfer data from the Alumni and Activities tables to the Complete_data table, where it became ready to be compiled. The VLOOKUP functions were wrapped into IFERROR functions, to avoid the creation of #N/A cells that could skew further analysis.
7. Compiled all relevant data into the Auxiliary table, which included the use of COUNTIF and COUNTIFS functions.
8. Created a Dashboard table which includes an "alumni per activity" table, as well as three graphs (alumni per state, alumni with teaching activities, and activity distribution per degree).


### Tables and their columns
Alumni

Column Name     | Data Type | Description

ID              | integer   | alumni ID

Degree          | text      | which degree was obtained

Graduation Year | integer   | year the degree was obtained

Activity        | text      | general activity category

Activities      | text      | specific activity

CVs             | text      | what kind of public CV the alumni has

Observations    | text      | further details


Activities

Column Name                  | Data Type | Description

ID                           | integer   | alumni ID

Degree                       | text      | which degree was obtained

Graduation Year              | integer   | year the degree was obtained

Activity                     | text      | general activity category

Current Role                 | text      | specific role

Other (current role)         | text      | role details

Role characteristics         | text      | legal classification of the role

Other (role characteristics) | text      | classification details

University/Company           | text      | institution where role is conducted

Country                      | text      | country of the institution

City                         | text      | city of the institution

State                        | text      | state/province of the institution


Complete_data

Columns extracted from Alumni and Activities



Auxiliary

Tables used for the dashboard


### Activity definitions
Although initially it might seem that some categories overlap, such as with Teaching and Education services, their exact definition lets us discriminate between different career paths.


Teaching: any teaching role where there is a definite contract between alumni and schools/universities, and which excludes services such as teaching English or other languages.

Research: any research role where there is a definite contract between alumni and schools/universities, encompassing both PhD candidates and Postdoc researchers.

Technical/administrative: bureaucratic roles, mostly within the public sector.

Education services: language teaching.

Private sector: all-encompassing category that inclues all alumni that work for the private sector outside of the other obvious categories, such as IT Services and analysts.

Consulting: roles that have as their job title the word "consultant", either in direct connection with a firm or with independent consulting.

Project coordination: often related to NGOs.

Cultural/artistic: roles pertaining to the arts, either through performance itself or va administrative roles related to the arts.

Freelancing: any role which is not encompassed by other categories, and that involves no definite contract between alumni and companies/universities/schools.

Analyst: generic term used by one of the data-gathering humans years ago, related to roles which have the word "analyst" in their job title.

Politics or social action: roles related to working directly with politicians or with social movements.

IT Services: roles directly related to the technology sector.
