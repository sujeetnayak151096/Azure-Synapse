# Project: Reading Different File Formats in Azure Synapse SQL Pool

## Table of Contents
- [Project Overview](#project-overview)
- [Environment Setup](#environment-setup)
- [Handling Different File Formats](#handling-different-file-formats)
  - [CSV File Format](#csv-file-format)
  - [JSON File Format](#json-file-format)
  - [Parquet File Format](#parquet-file-format)
- [Reading Multiple Files at Once](#reading-multiple-files-at-once)
- [Conclusion](#conclusion)

## Project Overview
The goal of this project is to demonstrate how to read different file formats such as CSV, JSON, and Parquet within Azure Synapse SQL Pool. Additionally, it covers processing multiple files in a folder using the `OPENROWSET` function.

## Environment Setup
- **Database Creation**: Created a new database called `sujeet_projects` to store external data sources and manage queries on various file types.
 ![image](https://github.com/user-attachments/assets/b11eae03-981b-4433-a210-bc1c9ae8cdb6)

- **External Data Source**: Created an external data source named `projectdatasets` pointing to the directory in Azure Data Lake where datasets are stored.

![image](https://github.com/user-attachments/assets/fba7101b-c2dc-4400-97bf-0f69d85ebe6c)


## Handling Different File Formats

### CSV File Format
- An external file format was created to read CSV files. The configuration specified essential parameters such as field terminators, row delimiters, and other formatting options according to Microsoft documentation.

![image](https://github.com/user-attachments/assets/eff3ffe6-8a3d-471f-b158-f0e29d80145c)

- **Querying CSV Files**: I have taken a CSV dataset of Olympics Medal 2024 Tally.
After creating the file format, the CSV file was successfully queried. The query extracts data such as rank, country, and the number of gold, silver, and bronze medals for each country.

![image](https://github.com/user-attachments/assets/3857b740-4a59-4602-8769-451b88de77fc)

![image](https://github.com/user-attachments/assets/9b27f446-d568-4d49-9d78-3ad3066d2288)

- After Successfully Querying the data, I try to Manipulate data and change the Column Name ‘Total’ AS ‘Total_Glory’ and Specify the Datatypes of Each Column.

![image](https://github.com/user-attachments/assets/88b813e1-fe45-4ce2-9e53-e1ececa5f32f)

![image](https://github.com/user-attachments/assets/5a2eb7d0-2d77-4f4f-94fd-391f021fc446)

- Then I Write a Query to Just Show me TOP 10 Countries with most Gold Medals USING ORDER BY Clause.

![image](https://github.com/user-attachments/assets/0468be60-c98a-43fd-a63e-08a4c782c54f)

![image](https://github.com/user-attachments/assets/fb15de74-b073-4030-929f-0a107b2f3905)


### JSON File Format
- **Dataset**: Used a JSON dataset of Amazon reviews for phone accessories.

![image](https://github.com/user-attachments/assets/b542408b-23b1-4705-b4fb-acf346fed1f6)

![image](https://github.com/user-attachments/assets/26aee14f-53f7-4ee5-9f4e-51b72b2e7229)


- **Querying JSON Files**: Extracted key fields like `reviewerID`, `reviewerName`, and `reviewText` from the JSON dataset.

![image](https://github.com/user-attachments/assets/d6946135-590d-42f4-bb8d-33a3287b2a72)

![image](https://github.com/user-attachments/assets/b3541c4e-f6b2-416f-b551-569494e06bab)


### Parquet File Format
- **Dataset**: Queried a Parquet file on school subjects covering lecture type, part, and concept.
- **Configuration**: Used a SAS Token for secure access and created an encryption master key. Defined an external file format for Parquet files and specified the file location in the data source.

![image](https://github.com/user-attachments/assets/55948d77-9e24-44df-9c12-88f8726b8818)

- Created MASTER KEY According to Microsoft Documentation and Created Database using SAS Token.
![MASTER KEY ](https://github.com/user-attachments/assets/a50972f5-3ca2-45d2-b916-5656a80f3297)

- Then Again Created the Data Source and Gave my Folder Location.

![image](https://github.com/user-attachments/assets/6c2972ac-4113-4284-84df-dc807ff64d3f)

- Created External file Format for Parquet File.
![image](https://github.com/user-attachments/assets/2ce7e0be-f7cd-4f96-b4a2-06cfad1f559d)

- My Dataset Consist of a Parquet file of a Particular Subject in School  which Consists of Lectured, Part, Type of Concept covered in that Lecture.
  I Write a Query to read all this data from a Parquet File.

  ![image](https://github.com/user-attachments/assets/a7d870dc-34e9-4804-9744-035643ce8eec)

  ![image](https://github.com/user-attachments/assets/78ee26c0-d5b6-4c64-a799-99d5f0540ec5)


## Reading Multiple Files at Once
To read multiple files, used a wildcard (`*.csv`) in the `BULK` parameter to load all files in the CSV folder at once. This folder contains details on cities, countries, and states (name, state_code, ID, latitude, and longitude).

![image](https://github.com/user-attachments/assets/87c0541a-57d3-4c6d-b44a-ebf7a2272054)  ![image](https://github.com/user-attachments/assets/e86a9858-a8c9-4686-9158-c26ea186f33d)

-   Write a Query to read all .csv File inside a CSV Folder using /*.csv
![image](https://github.com/user-attachments/assets/f92d40c6-c6fd-428e-a46a-8425c2fd02f3)

![image](https://github.com/user-attachments/assets/f2e2492e-b2a9-48aa-9472-d9b1ee0f67ff)



## Conclusion
This project demonstrates the use of Azure Synapse SQL Pool to efficiently read and process different file formats including CSV, JSON, and Parquet files. It also covers the use of wildcard matching to process multiple files at once from a folder, showcasing the versatility of Synapse for handling large datasets from various sources.

---

Data Engineer: Sujeet Nayak
