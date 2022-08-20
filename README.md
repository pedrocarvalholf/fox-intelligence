# French App Market during 2020

### A data analysis of the french app market during 2020, the goal is to understand the impact of COVID-19 confinement in France

## Sumary

* [General Information](https://github.dev/pedrocarvalholf/fox-intelligence/#general-information)
* [Data Description](https://github.dev/pedrocarvalholf/fox-intelligence/#data-description)
* [Libs Used](https://github.dev/pedrocarvalholf/fox-intelligence/#libs-used)
* [Project Layout](https://github.dev/pedrocarvalholf/fox-intelligence/#project-layout)
* [Contact](https://github.dev/pedrocarvalholf/fox-intelligence/#contact)

## General Information
  This project intends to solve two problems:

  1) Enrich the table extract to add an app title and editor name for each record by matching the images behind each URL with the ones in the external source extract

  2) Analyze the enriched extract and make a short presentation aimed at app editors with my conclusions on the impact of the Covid confinement in France

  I've solved the first problem in the notebook 'Data Cleaning, Join Tables' and the second one in the notebook 'Data Visualization, Analysis'

## Data Description
  There are two .csv files to work in this project, they're non-structured and the first objective of the project is to structure them.

  `technical_test_table_extract:`

    id_order: id of a single purchase
    year_month: year and month of the purchase,
    order_total_paid: price paid for a app feature,
    product_name: name of the feature,
    product_url_img: url link for image's editor of the app
    technical_test_external_source_extract:
    title: name of the company,
    editor: editor of the company,
    icon: url link for the icon's editor of the app

 ## Libs Used

- [Pandas](https://pandas.pydata.org/)
- [Numpy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [Jupyter Notebook](https://jupyter.org/)

 ## Project Layout

 **Part One:** Data Cleaning, Join Tables

 The main difficulty of this project is how to structure these two tables, because a SQL-based operation will not work.
 Initially, I've reduced both datasets, technical_test_table_extract.csv using the repeated urls from product_url column. This operation allowed me to reduce the dataset from 32k rows to 160 rows.

 After this I scrapped the dataframes and saved the images from product_url_img and icon in different folders.

 The next part I've compared both datasets using cosine similarity of the pixels images to find similar enough pictures between the datasets, and classify the title and editor column based on this.
 By here I've obtained a reduced dataset with correct classification for 'title' and 'editor'.
 After obtaining the reduced dataset of 160 rows with 'title' and 'editor' information, I've compared the technical_test_table_extract to the reduced one to paste these two rows based on the equals 'product_url_img'. After this I've obtained the 'enriched_table', a dataset structured from both original datasets.

 **Part Two:** Data Visualization, Analysis

 In this section I analyze what the total profit of the companies and make some visualizations.

 Also, the goal of this notebook is to investigate the following metrics:

1) total profit from each company during the period

2) Month profit of each company

3) Month profit per feature of each company

Using the graphics plotted in this part I've made a [presentation](https://github.com/pedrocarvalholf/fox-intelligence/blob/main/App%20Market%20in%20France%20during%202020.pdf) in canva.com, aimed at app editors.

## Contact

Feel free to contact me about some project, idea or anything!

I believe learning is a life long journey and I'm open to hearing from anyone.

Thanks!

https://www.linkedin.com/in/pedrocarvalholf/

pedrocarvalholf@gmail.com
