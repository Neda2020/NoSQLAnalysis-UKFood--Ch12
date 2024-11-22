
# UK Food Standards Agency - Data Analysis for Eat Safe, Love

## Project Background
The UK Food Standards Agency evaluates various establishments across the United Kingdom, assigning them a food hygiene rating. The ratings, ranging from 1 to 5, reflect the overall hygiene and safety standards of the establishments. Higher ratings indicate better conditions.

This project is part of a collaboration with **Eat Safe, Love**, a food magazine, to analyze this dataset. The insights derived will guide their journalists and food critics in deciding where to focus future articles and highlight key establishments worth featuring or avoiding.

---

## Project Overview
The project is divided into three main parts:

### Part 1: Database and Jupyter Notebook Setup
This section involves setting up the MongoDB database and importing the data provided in `establishments.json`. Key steps include:

- **Data Import**: Using the `mongoimport` command to create a MongoDB database (`uk_food`) and a collection (`establishments`) with the provided dataset.
- **Validation**: Verifying the database and collection were created successfully by listing the databases and collections and displaying a sample document.
- **Database Preparation**: Assigning the `establishments` collection to a variable to enable further queries.

### Part 2: Database Updates
In this section, modifications were made to the database based on requests from the magazine editors:

1. **Adding a New Restaurant**:
   - A halal restaurant, "Penang Flavours," located in Greenwich, was added to the database. The new entry included essential fields such as `BusinessName`, `BusinessType`, `geocode`, and `LocalAuthorityName`.
   
2. **Updating `BusinessTypeID`**:
   - The `BusinessTypeID` for "Restaurant/Cafe/Canteen" was queried and updated for "Penang Flavours."

3. **Removing Unwanted Data**:
   - Establishments in the Dover Local Authority were removed from the database, as requested by the editors.

4. **Data Cleaning**:
   - Fields like `latitude`, `longitude`, and `RatingValue` were converted to appropriate data types (decimal and integer) to standardize the dataset.

### Part 3: Exploratory Analysis
This section involves answering specific questions to guide the magazine's content strategy:

1. **Establishments with a Hygiene Score of 20**:
   - Identified establishments with a poor hygiene score of 20, indicating serious hygiene issues. These establishments are critical to highlight in articles focusing on food safety.
   - Results were displayed using Pandas DataFrames for clarity.

2. **Establishments in London with a `RatingValue` ≥ 4**:
   - Queried establishments located in London with high `RatingValue`, showcasing exemplary establishments for potential recommendations.

3. **Top 5 Establishments Near "Penang Flavours"**:
   - Identified the top 5 establishments with a `RatingValue` of 5, located within a 0.01-degree proximity of "Penang Flavours." These establishments were sorted by the lowest hygiene score to evaluate competition.

4. **Local Authority Areas with the Most Establishments Scoring 0 in Hygiene**:
   - Used an aggregation pipeline to find Local Authorities with the highest number of establishments scoring 0 in hygiene. The results were sorted and presented, providing insights into areas needing improvement.

---

## Tools and Technologies
- **Database**: MongoDB
- **Programming Language**: Python
- **Libraries**:
  - `pymongo` for MongoDB interactions.
  - `pandas` for data manipulation and visualization.
  - `pprint` for structured output of database documents.

---

## Output and Results
The results of the analysis include:

- Cleaned and structured data ready for further exploration.
- Specific insights into hygiene and ratings trends.
- Actionable data for content planning by **Eat Safe, Love**.

---

## How to Run the Project
1. Clone the repository.
2. Import the data into MongoDB using the provided `mongoimport` command.
3. Run the Jupyter notebooks (`NoSQL_setup_starter.ipynb` and `NoSQL_analysis_starter.ipynb`) to reproduce the results.
