# MENTAL HEALTH IN TECH INDUSTRY EDA
An Exploratory Data Analysis of a survey done about mental health issues in tech industry spanning the course of 4-5 years
The project focuses on analyzing survey responses to extract and visualize trends in mental health conditions over multiple years

## Technologies Used
- Python (Pandas, Seaborn, Matplotlib)
- SQLite for data storage and querying
- Jupyter Notebook for interactive analysis

## SQLite Integration

SQLite is used in this project to store, query, and manage the survey data. The following steps outline the SQLite integration process:

1. **Database Creation:**
The survey data is stored in an SQLite database, with separate tables for survey responses and metadata.

2. **Combining Tables:**
To facilitate analysis, multiple tables were combined into a single table named CombinedTable. SQL query below was used to achieve this.

    ```SQL
    CREATE TABLE CombinedTable AS
    SELECT r.ResponseID, r.AnswerText, s.SurveyDescription, s.SurveyID
    FROM Responses r
    JOIN Surveys s ON r.SurveyID = s.SurveyID;
    ```

3. **Querying the database:**
Data is retrieved using Python's sqlite3 module and processed with Pandas for further analysis. For example, the following query retrieves data from the combined table:
    ```Python
    query = "SELECT * FROM CombinedTable"
    df = pd.read_sql_query(query, conn)
    ```
## Setup
To set up the project, follow these steps:

1. Clone repository 
```bash
git clone <https://github.com/bondpapi/MENTAL-HEALTH-IN-TECH-INDUSTRY-EDA>
```

2. Install the required Python libraries:
```bash
pip install pandas matplotlib sqlite3
```

3. Ensure the SQLite database is available in the project directory.

## Usage

Extract mental health conditions from survey responses by running the analysis script.

Visualize trends using the generated box plots and bar charts.

Modify the known conditions list in the script to include additional keywords if needed.

## License

This project is licensed under the MIT License. See the LICENSE file for details
