# Create database

```SQL
CREATE DATABASE worldcup;
```
# Connect to database

```SQL
\c worldcup
```

# Create table teams

```SQL
CREATE TABLE teams();
```

## Add columns to teams table

```SQL
ALTER TABLE teams ADD COLUMN team_id SERIAL PRIMARY KEY;
ALTER TABLE teams ADD COLUMN name VARCHAR(30) UNIQUE;
```

## Add NOT NULL constraints

```SQL
ALTER TABLE teams ALTER COLUMN team_id SET NOT NULL;
ALTER TABLE teams ALTER COLUMN name SET NOT NULL;
```

# Create table games

```SQL
CREATE TABLE games();
```

## Add columns to games table

```SQL
ALTER TABLE games ADD COLUMN game_id SERIAL PRIMARY KEY;
ALTER TABLE games ADD COLUMN year INT;
ALTER TABLE games ADD COLUMN round VARCHAR(50);
ALTER TABLE games ADD COLUMN winner_id INT REFERENCES teams(team_id);
ALTER TABLE games ADD COLUMN opponent_id INT REFERENCES teams(team_id);
ALTER TABLE games ADD COLUMN winner_goals INT;
ALTER TABLE games ADD COLUMN opponent_goals INT;
```

## Add NOT NULL constraints

```SQL
ALTER TABLE games ALTER COLUMN game_id SET NOT NULL;
ALTER TABLE games ALTER COLUMN year SET NOT NULL;
ALTER TABLE games ALTER COLUMN round SET NOT NULL;
ALTER TABLE games ALTER COLUMN winner_id SET NOT NULL;
ALTER TABLE games ALTER COLUMN opponent_id SET NOT NULL;
ALTER TABLE games ALTER COLUMN winner_goals SET NOT NULL;
ALTER TABLE games ALTER COLUMN opponent_goals SET NOT NULL;
```
