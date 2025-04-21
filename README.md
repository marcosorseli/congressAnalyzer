# Analysis of Brazilian Deputies' Voting Patterns (2024)

This project analyzes the roll-call voting records from Brazil's Chamber of Deputies (Câmara dos Deputados) for the year 2024. It uses unsupervised machine learning techniques (PCA and K-Means clustering) to identify distinct voting blocs among deputies, assess political party cohesion, and visualize the potential ideological composition of parties based on legislative behavior.

## Motivation
Brazil's multi-party political system often results in complex legislative dynamics. This project seeks to objectively identify underlying voting alignments among federal deputies in 2024, moving beyond party labels alone. The goal is to understand how deputies cluster based on their actual votes, how unified parties are, and how these data-driven clusters map onto the commonly understood Left-Center-Right spectrum.

## Data Source
The roll-call voting data used in this analysis covers the period from January 1, 2024, to December 31, 2024. It was obtained from the official Dados Abertos portal of the Câmara dos Deputados: https://dadosabertos.camara.leg.br/ or specific dataset link if available.

**Note:** The data file (`voting_data_2024.csv`) is included in this repository.

## Installation / Setup

## Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/marcosorseli/congressAnalyzer](https://github.com/marcosorseli/congressAnalyzer)
    cd congressAnalyzer
    ```
2.  **Create the environment (using `venv`):**
    ```bash
    python -m venv venv
    ```
    (This creates a folder named `venv` in your project directory. Ensure `venv/` is listed in your `.gitignore` file!)

3.  **Activate the environment:**
    * On macOS/Linux:
        ```bash
        source venv/bin/activate
        ```
    * On Windows (Git Bash):
        ```bash
        source venv/Scripts/activate
        ```
    * On Windows (Command Prompt/PowerShell):
        ```cmd
        venv\Scripts\activate.bat
        # or
        venv\Scripts\Activate.ps1
        ```
    (Your terminal prompt should change to indicate the environment is active, often showing `(venv)` at the beginning).

4.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt


## Usage

1.  Ensure all dependencies are installed and the data file is correctly placed (if needed).
2.  Launch Jupyter Lab or Jupyter Notebook:
    ```bash
    jupyter lab
    # or
    jupyter notebook
    ```
3.  Open the `your_notebook_name.ipynb` file.
4.  Run the cells sequentially from top to bottom. The notebook includes data loading, preprocessing, PCA, clustering, cohesion analysis, composition analysis, and visualizations.

**Alternatively, using Google Colab:**
1.  Upload the notebook (`your_notebook_name.ipynb`) to Google Colab (`File` > `Upload notebook`).
2.  Handle data access within Colab by either:
    * Uploading the `voting_data_2024.csv` file directly when prompted by the notebook (if using the `files.upload()` method).
    * Mounting your Google Drive (`drive.mount('/content/drive')`) and ensuring the data file is in the correct Drive path specified in the notebook.
3.  Run the cells sequentially.

## Methodology
The core analysis follows these steps:
1.  **Data Loading & Preprocessing:** Reads the raw voting data, cleans it, and encodes votes numerically (e.g., Sim=1, Não=-1, Others=0).
2.  **Feature Engineering:** Creates a matrix where rows are deputies and columns represent their votes on specific bills.
3.  **Dimensionality Reduction:** Applies Principal Component Analysis (PCA) to reduce the dimensionality of the vote matrix, capturing the main axes of voting variation.
4.  **Clustering:** Uses the K-Means algorithm on the PCA components to group deputies into 3 clusters (hypothesized as Left/Center/Right).
5.  **Interpretation & Analysis:** Assigns ideological labels to clusters based on party composition, calculates party cohesion scores, and analyzes the cluster makeup of different parties.
6.  **Visualization:** Uses Matplotlib and Seaborn to visualize the results (PCA scatter plot, cohesion bars, composition bars).

## Key Findings
* The analysis successfully identified three distinct voting clusters among deputies in 2024 based on PCA and K-Means.
* Party cohesion varies significantly, with parties like PSOL showing high unity and MDB displaying more fragmented voting.
* The cluster composition analysis reveals that some parties are ideologically homogeneous according to voting patterns, while others draw members from multiple clusters (e.g., UNIAO has representation in all three clusters, Left, Right and Center).

## Limitations
* The interpretation of clusters as 'Left', 'Center', 'Right' is based on observed party compositions and external knowledge, containing inherent subjectivity.
* The analysis relies solely on roll-call votes and does not incorporate other aspects of legislative behavior or political alignment.

## License
This project is distributed under the terms of the MIT License. You can find the full license text in the [LICENSE](LICENSE) file.

## Contact

Marcos Orseli - [https://github.com/marcosorseli](https://github.com/marcosorseli)