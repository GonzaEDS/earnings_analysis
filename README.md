# Earnings Data Analysis

This repository contains a script to analyze earnings data from Outlier, combining data from multiple pay cycles into a single DataFrame and generating various visualizations and summary statistics.

## Requirements

The following Python packages are required to run the script:

- pandas==1.5.3
- matplotlib==3.7.1
- seaborn==0.12.2

### Setting Up a Virtual Environment

It's recommended to create a virtual environment to manage dependencies and avoid conflicts with other projects. You can set up a virtual environment as follows:

1. Create a virtual environment:

   ```bash
   python -m venv venv
   ```

2. Activate the virtual environment:

   - On Windows:

     ```bash
     venv\Scripts\activate
     ```

   - On macOS and Linux:

     ```bash
     source venv/bin/activate
     ```

3. Install the required packages using the provided `requirements.txt` file:

   ```bash
   pip install -r requirements.txt
   ```
## File Structure

```
.
├── pay-periods/         # Folder containing the CSV files with earnings data
├── combined_earnings.csv  # Output file containing combined earnings data
├── earnings_analysis.ipynb   # Script for processing data and generating visualizations
├── requirements.txt       # List of required Python packages
└── README.md              # This README file
```
### Example
![alt File Structure Example](https://i.imgur.com/NTtPlpP.png)

Replace the file `this_pay_cycle.csv` for the new version or the new finished cycle to update the stats.

## Script Details

### Combining CSV Files

The script reads all CSV files from the `pay-cycles` folder and combines them into a single DataFrame. The combined data is saved as `combined_earnings.csv`.

### Data Cleaning and Processing

- **Date Conversion:** The script converts the `workDate` column to a datetime format, handling multiple possible date formats.
- **Payout Conversion:** The `payout` column is converted to numeric by removing the dollar sign and converting the values to floats.
- **Duration Conversion:** The `duration` column is converted to seconds, and missing durations are imputed with the median duration.

### Visualizations

The script generates the following visualizations using Seaborn and Matplotlib:

- **Earnings by Day:** A bar plot showing total earnings for each day.
- **Number of Tasks Completed by Day:** A bar plot showing the number of tasks completed each day.
- **Total Duration by Day:** A bar plot showing the total hours worked each day.
- **Earnings by Week:** A bar plot showing total earnings for each week.

### Summary Statistics

The script calculates and displays the following summary statistics:

- Total hours worked
- Total tasks completed
- Total earnings
- Average earnings per day, week, month, and hour
- Average tasks completed per day, week, and month
- Average hours worked per day, week, and month

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements

- [Pandas Documentation](https://pandas.pydata.org/pandas-docs/stable/)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
- [Seaborn Documentation](https://seaborn.pydata.org/)

## Features

- Combine multiple CSV files into a single DataFrame
- Convert and normalize date formats
- Clean and process payout and duration data
- Generate bar plots for:
  - Earnings by day
  - Number of tasks completed by day
  - Total duration (in hours) by day
  - Earnings by week
- Display summary statistics in a table format