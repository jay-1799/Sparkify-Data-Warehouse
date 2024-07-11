**Project: Data Modeling for Music Streaming App Analysis with PostgreSQL**

This project creates a PostgreSQL data model and ETL pipeline to analyze song play data for a music streaming app.

**Data Model**

The star schema model consists of:

- **Fact Table:** `songplays` - Stores song listening events with user, song, and time information.
- **Dimension Tables:**
  - `users`: User information (ID, name, gender, subscription level).
  - `songs`: Song information (ID, title, artist, year, duration).
  - `artists`: Artist information (ID, name, location).
  - `time`: Time data extracted from songplays (start time, hour, day, week, month, year, weekday).

**ETL Pipeline**

The Python script `etl.py` performs the following:

1. Connects to the PostgreSQL database.
2. Processes song data files and inserts data into `songs` and `artists` tables.
3. Processes log data files:
   - Extracts time data and inserts it into the `time` table.
   - Inserts user data into the `users` table.
   - Inserts song play records into the `songplays` table, leveraging an index on `artist_id` for efficient joins.
4. Disconnects from the database.

**SQL Queries**

The Python script `sql_queries.py` contains:

- CREATE table statements for all tables.
- INSERT statements for populating tables.
- Select queries for joining tables and performing analysis.

**Example Queries**

The readme showcases example queries to analyze user activity and popular songs/artists.

**Getting Started**

1. Install required Python libraries (e.g., psycopg2).
2. Configure database connection details in `etl.py`.
3. Run `etl.py` to execute the ETL pipeline.
4. Use `sql_queries.py` or a SQL client to interact with the database and perform further analysis.
