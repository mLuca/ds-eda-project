# King County Housing EDA Project Template

This is the starter template for the Exploratory Data Analysis (EDA) project. You will work with the King County housing dataset (home sales in and around Seattle, USA), uncover what drives house prices, and turn your findings into insights and recommendations for a client you choose.

## Learning Objectives

By the end of this repository, you should be able to:

- Connect to a PostgreSQL database from Python and load query results into a pandas DataFrame.
- Frame an exploratory data analysis around clear research questions and hypotheses.
- Clean and wrangle a real-world dataset by handling missing values, outliers, and feature transformations.
- Explore distributions and the relationships between features and the target variable (price).
- Translate your analysis into at least three insights and three client-specific recommendations.
- Present your work to a non-technical audience.

## Learning Path

Work through the files in order. Start with the assignment to understand the goal, follow the workflow as your guide, fetch the data, then run your analysis in the EDA notebook.

> [!TIP]
> The data lives in the **eda** schema of the database and is split across two tables. Before fetching anything in code, connect with DBeaver and explore that schema: inspect both tables, check [**Column Names**](column_names.md) for what each field means, and work out how to join them. Once you have a working `JOIN`, use it as the query in [**03 - Fetching the Data**](03_fetching_the_data_eda.ipynb) to load the combined dataset into pandas.

| File / Folder                                                   | Description                                                                                                              |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| [**01 - Assignment**](01_assignment.md)                      | The project brief: the dataset, your tasks, deliverables, and the list of clients to choose from.                        |
| [**02 - Workflow**](02_workflow.md)                          | A recommended EDA workflow, from understanding and questioning the data through cleaning, relationships, and presenting. |
| [**03 - Fetching the Data**](03_fetching_the_data_eda.ipynb) | Connect to the PostgreSQL database with psycopg2 and SQLAlchemy, then pull the data into a pandas DataFrame.             |
| [**04 - EDA**](04_eda.ipynb)                                 | Starter notebook for your exploratory data analysis.                                                                     |
| [**Column Names**](column_names.md)                          | Data dictionary describing each column in the King County housing dataset.                                               |

### Additional Folders and Files

| File / Folder                           | Description                                                                                    |
| --------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [**Data**](data/)                    | Where you save the dataset CSV. The folder is tracked, but its data files are kept out of git. |
| [**.env.example**](.env.example)     | Template for the database credentials. Copy it to `.env` and fill in your values.            |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies.                                                        |
| [**uv.lock**](uv.lock)               | Dependency lock file.                                                                          |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >` brackets, with your own value. For example, `cd <repo-name>` becomes `cd ds-eda-project-template`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.
---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in `.venv/`.

```bash
cd <repo-name>
uv sync
```

> [!TIP]
> Need a library that is not installed yet (for example a mapping)? Add it with `uv add <package-name>`. This updates `pyproject.toml` and `uv.lock` and installs it into your `.venv`. Commit both files; teammates then run uv sync after pulling to get the same environment.

---

### 5. Set up your Database Credentials

The data-fetching notebook reads the database connection details from a `.env` file. Copy the template and fill in your own values:

```bash
cp .env.example .env
```

Open `.env` and replace the placeholders with the credentials for the King County housing database (the same ones you use in DBeaver). These values feed [**03 - Fetching the Data**](03_fetching_the_data_eda.ipynb).

> [!CAUTION]
> `.env` holds secrets and must never be committed. It is already listed in `.gitignore`. Only `.env.example`, with placeholder values, belongs in the repository.

---

### 6. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by uv sync.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**House Sales in King County dataset**](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction): The source dataset, with column descriptions and community notebooks.
- [**Pandas user guide**](https://pandas.pydata.org/docs/user_guide/index.html): The official guide to data manipulation with pandas.
- [**Seaborn tutorial**](https://seaborn.pydata.org/tutorial.html): Statistical data visualization in Python.
- [**SQLAlchemy documentation**](https://docs.sqlalchemy.org/en/20/): The database toolkit used to query PostgreSQL from Python.
- [**Hypothesis generation for EDA**](https://www.analyticsvidhya.com/blog/2020/11/an-efficient-way-of-performing-eda-hypothesis-generation/): How to form research questions and hypotheses before diving into the data.
- [**EDA Checklist**](https://github.com/neuefische/datascience-infographics/blob/main/EDA_Checklist.md): A phase-by-phase checklist for working through an exploratory analysis.
- [**Detailed EDA with Python**](https://www.kaggle.com/code/ekami66/detailed-exploratory-data-analysis-with-python): A worked example of a thorough EDA notebook on real data.
- [**Tips for data science presentations**](https://www.dataknowsall.com/storytelling.html): Storytelling techniques for presenting results to a non-technical audience.
