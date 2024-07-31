# shelf-space-calculator
A calculator to allocate library shelf space, as informed by historic subclass expansion, using Alma Analytics reports and space measurements

## Description

This project is designed to calculate and manage the space utilization of library shelves in a way that is informed by the expansion of each subclass, or part of a subclass, over a defined time period. It includes tools for measuring and analyzing the total, occupied, and free space on library shelves and for calculating free space necessary for expansion based on historic acquisition patterns. 


## Features

- Input total and occupied shelf space to calculate free space for the an entire library, room or section, as well as for every single shelf, allocating different percentages of free space in each Library of Congress subclass or part of subclass based on projected growth. 
- Data processing for shelf maps and subclass data using Pandas.
- Designed to run in a Colab environment.

## Installation

To run this script, you need to have Python installed along with the following libraries:
- Pandas

You can install the required libraries using pip:

```bash
pip install pandas
```

## Usage

1. Prepare the data input files. The data file subclass_data originates in an Alma Analytics report on historical acquisitions patterns broken down by subclass, integrated with measurements of the linear cm occupied by each subclass (see the Analytics XML file). The data file shelf_map originates from a mapping of the banks of shelving in the relevant section of the library. Sample Excel files are provided. 
2. Ideally, import this repository into Google Colab as a new notebook.
3. Create a folder structure in Colab with the path `content/files/inputs`.
4. Upload the necessary data files (`shelf_map.xlsx` and `subclass_data.xlsx`) into the `inputs` folder.  
5. Run the script. The space allocations will be saved as an Excel file at content/files/outputs.
6. Download the Excel file 'outputs'.

### Example

```python
# Enter the total shelf space in cm
total_space_in_cm = int(input("Enter the total shelfspace in cm. of the area: "))
print(f"You entered: {total_space_in_cm}")

# Enter the total occupied shelf space in cm
total_occupied_space_in_cm = int(input("Enter the total occupied shelfspace in cm. of the area: "))
print(f"You entered: {total_occupied_space_in_cm}")

# Calculate the total free space
total_free_space_in_cm = total_space_in_cm - total_occupied_space_in_cm
print(f"Total free space: {total_free_space_in_cm}")
```

## Data Preparation

1. Prepare the shelf map and save it as `shelf_map.xlsx`. The file should contain columns for shelf ID and length (cm).
2. Prepare the subclass data and save it as `subclass_data.xlsx`. The file should contain columns for subclass and growth as a proportion of all volumes from FY20-24, and a column "total occupied" with cm occupied by each subclass.

## Note

The accuracy of the space calculations depends on the accuracy of the lengths and numbers of shelves and the measurements of occupied space. Ensure that the data files are correctly formatted and contain accurate information.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- The script was automatically generated by ChatGPT, further developed in Colab and manually tweaked for accuracy and to reflect the conceptualisation of the acquistion history-based space allocation policy by donnellop. Readme created in conjunction with ChatGPT!

