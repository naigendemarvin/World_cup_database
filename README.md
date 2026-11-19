
World Cup Database

A PostgreSQL relational database and Bash automation suite built for the freeCodeCamp Relational Database Certification. The project parses historical World Cup match data from games.csv, populates a normalized PostgreSQL database, and runs analytical SQL queries via shell scripts.

Project Structure

• worldcup.sql — Complete PostgreSQL database dump containing the worldcup schema (teams and games tables) and all inserted match records.
• insert_data.sh — Bash script that reads games.csv, inserts unique teams into teams, resolves foreign key IDs, and populates the games table.
• queries.sh — Bash script that executes SQL queries against worldcup to compute tournament statistics, goal totals, averages, and champions.


Database Schema

• teams
	• team_id (SERIAL PRIMARY KEY NOT NULL)
	• name (VARCHAR UNIQUE NOT NULL)
• games
	• game_id (SERIAL PRIMARY KEY NOT NULL)
	• year (INT NOT NULL)
	• round (VARCHAR NOT NULL)
	• winner_id (INT NOT NULL REFERENCES teams(team_id))
	• opponent_id (INT NOT NULL REFERENCES teams(team_id))
	• winner_goals (INT NOT NULL)
	• opponent_goals (INT NOT NULL)

Technologies Used

• PostgreSQL
• Bash / Shell Scripting
• SQL
  
