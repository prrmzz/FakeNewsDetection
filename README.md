# 1. Libraries Used

folium: Creates interactive maps for geographic visualization.
pandas: Handles data in tabular form.
numpy: Generates random data and performs numerical computations.
scikit-learn:
MinMaxScaler: Normalizes numerical data.
RandomForestClassifier: Builds a machine learning model to classify locations as suitable or unsuitable.
train_test_split: Splits the dataset into training and testing subsets.
accuracy_score: Evaluates model performance.
IPython.display: Displays the map directly in Jupyter Notebook.

# 2. Simulating Persian Gulf Data
The Persian Gulf's coordinates range from:

Latitude: 24°N to 30°N
Longitude: 48°E to 56°E
Data Features:
Latitude (latitude): Generated randomly between 24°N and 30°N.
Longitude (longitude): Generated randomly between 48°E and 56°E.
Global Horizontal Irradiance (ghi): Simulated solar irradiance values (4–8 kWh/m²/day).
Elevation (elevation): Simulated terrain elevation (0–500 meters).
This data is stored in a Pandas DataFrame.

# 3. Data Normalization

To standardize data for machine learning, the script uses MinMaxScaler to scale values between 0 and 1:

scaled_ghi: Normalized solar irradiance.
scaled_elevation: Normalized elevation values.

# 4. Adding Suitability Labels
A new column, suitable, is created based on whether a location's ghi exceeds the median irradiance:

1: Suitable for solar panels (high irradiance).

0: Unsuitable for solar panels (low irradiance).

# 5. Building the Machine Learning Model
A Random Forest Classifier is trained to classify locations as "suitable" or "unsuitable" based on:
scaled_ghi: Normalized solar irradiance.
scaled_elevation: Normalized elevation.
The data is split into:
Training set (80%): Used to train the model.
Testing set (20%): Used to evaluate model accuracy.
Output:
The accuracy score measures how well the model predicts suitability.

# 6. Visualizing the Map
Using folium, the script generates an interactive map:

Markers:
Green markers: Suitable locations.
Red markers: Unsuitable locations.
The map is centered at [27, 52] (middle of the Persian Gulf).
The final map is saved as persian_gulf_solar_map.html.

# 7. Displaying the Map in Jupyter Notebook
To render the map in Jupyter:

The IPython.display.IFrame class embeds the saved HTML map.
This allows interactive exploration directly within the notebook.

# 8. Output Files
persian_gulf_solar_map.html:
The interactive map file.
Open it in any browser to view the results.
