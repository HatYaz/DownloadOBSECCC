This Python script is designed to download hourly climate observations data from the Meteorological Service of Canada (Only Quebec for now !!) for a specified weather station and time range. It then allows users to visualize this data by plotting a wind rose using PySimpleGUI and Matplotlib.

url: https://dd.meteo.gc.ca/climate/observations/hourly/csv/QC/

Here's a breakdown of the code:

1. **Imports**: The script imports necessary libraries, including `os`, `requests`, `pandas`, `PySimpleGUI`, `io`, `matplotlib.pyplot`, `numpy`, and `FigureCanvasTkAgg` from `matplotlib.backends.backend_tkagg`.

2. **Function Definitions**:
   - `download_data`: This function downloads hourly climate observations data from the specified weather station (`st_id`) and time range (`year_start` to `year_end`). It constructs the URL for each year's data, checks if the file exists, downloads it, and saves it into a DataFrame. Finally, it merges all dataframes into one and saves it to a CSV file in the specified output folder.
   - `plot_wind_rose`: This function reads the CSV file containing climate data, filters out rows with missing wind direction or wind speed values, categorizes wind directions, calculates mean wind speed for each direction category, and creates a wind rose plot using Matplotlib. The wind rose plot is then embedded into a PySimpleGUI window.

3. **GUI Layout**: The GUI layout is defined using PySimpleGUI. It includes input fields for station ID, start year, end year, and output folder, as well as buttons for downloading data and plotting the wind rose. The wind rose plot is displayed in a canvas within the GUI window.

4. **Event Loop**: The script enters a event loop using PySimpleGUI, where it waits for user interaction. If the user clicks the "Download" button, it calls the `download_data` function. If the user clicks the "Plot Wind Rose" button, it prompts the user to select a CSV file containing climate data and then calls the `plot_wind_rose` function.

Overall, this script provides a user-friendly interface for downloading and visualizing climate data from the Meteorological Service of Canada.
