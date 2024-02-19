# DBT-command

## 1. Check the environment to ensure all necessary dependencies and components are installed and configured correctly.

```
dbt debug 
```

## 2. Execute a data model

This command tells dbt to compile your model SQL files into runnable SQL code and then execute that code against your data warehouse. The purpose of this is to transform raw data into a structured format suitable for analysis, according to the transformations defined in your dbt models.

```
dbt run
```

## 3. To load data from CSV files into your data warehouse. 

This feature is particularly useful for managing small pieces of static or reference data that you want to version control alongside your dbt models. Examples of such data might include currency exchange rates, country codes, or any other relatively small dataset that changes infrequently.

### How to Use dbt seed
Prepare Your CSV Files: First, you need to have your data in CSV format. Place these CSV files in the seeds directory of your dbt project. If the seeds directory does not exist, you can create it.

Configure Your Seed Files (Optional): You can configure the behavior of dbt seed in your dbt_project.yml file. This can include specifying how dbt should treat headers, data types, or even the schema where your seed tables should be created.

Run the Command: Execute the dbt seed command from the terminal in your dbt project directory. This will load the data from your CSV files into your data warehouse, creating new tables or replacing existing ones with the names matching your CSV file names.

```
dbt seed
```

### Common Options for dbt seed
--select or -s: This option allows you to run dbt seed for specific seed files only, rather than all seed files in your project.

--full-refresh: If you want to drop and recreate the seed tables instead of inserting data into them, you can use this option. This is useful if the structure of your CSV files has changed (e.g., columns were added or removed).

--show: This option will print the compiled SQL to the terminal for the seed operation, which can be useful for debugging or understanding how dbt translates your CSV files into SQL commands.


## 4. Compile

The dbt compile command is a fundamental part of the dbt (data build tool) workflow, focusing on preparing your dbt project's SQL code for execution against a data warehouse without actually running the transformations. This command parses your project's model files, macros, tests, and seed files, then generates the raw SQL code that would be executed if you were to run dbt run. The output of dbt compile is a set of .sql files stored in the target directory of your dbt project.


```
dbt compile
```

### When to Use dbt compile

'Debugging and Testing': Before running your transformations, you might want to inspect the SQL that dbt generates to ensure it's doing what you expect. dbt compile allows you to see the exact SQL statements dbt will execute, making it easier to debug and test your code.

Code Review: The compiled SQL can be reviewed by team members for coding standards, optimization, and to ensure business logic is correctly implemented. This is especially useful in teams where not everyone might be familiar with dbt's templating language (Jinja).

Integration with Other Tools: In some cases, you might want to use the compiled SQL with other tools or processes outside of dbt. For example, you might have a custom deployment process that requires reviewing or modifying the SQL before execution.