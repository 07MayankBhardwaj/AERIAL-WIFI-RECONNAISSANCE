![WhatsApp Image 2023-05-19 at 11 51 12 AM](https://github.com/07MayankBhardwaj/AERIAL-WIFI-RECONNAISSANCE/assets/127011697/d89a5dfb-802d-426a-b76f-56f2b0c396eb)

GROUP: Mayank Bhardwaj, Asutosh Kumar, Sanskar , Suman Thapa

University----> UPES,Dehradun

Date - 1st-april-1st-May

### Title: War Flight Reconnaissance: Aerial Wardriving Project

## Abstract:
This report presents a detailed description of a war flight reconnaissance project that utilized wardriving techniques. The project involved the deployment of an ESP8266 + R1 mini hardware peripherals strapped to a Mavic Pro quadcopter, along with a NEO 6m GPS module and an SD Logger mini for ESP8266. Additionally, an Arduino UNO was used to capture data separately. The primary objective was to collect wardriving data during an aerial reconnaissance test conducted in the vicinity of UPES Bidholi, where our university is located. This report outlines the steps involved in the project, highlights the hardware components and software used, and provides insights into the data capture and analysis process.

## 1. Introduction:
The rapid advancements in Internet of Things (IoT) and unmanned aerial vehicles (UAVs) have opened up new possibilities for innovative applications. In this project, we aimed to leverage these technologies to create a war flight reconnaissance system capable of capturing wardriving data from a bird's-eye view. By integrating various hardware components and software, we successfully conducted an aerial reconnaissance test near UPES Bidholi.

## 2. Hardware Components:
2.1 ESP8266 + R1 mini: The ESP8266 microcontroller was utilized as the core hardware component, providing wireless connectivity and data processing capabilities.
2.2 Mavic Pro Quadcopter: The Mavic Pro was chosen as the UAV platform due to its stability, maneuverability, and payload capacity.
2.3 NEO 6m GPS Module: The GPS module enabled precise positioning and navigation of the quadcopter during the reconnaissance flights.
2.4 SD Logger Mini for ESP8266: The SD Logger mini facilitated the logging and storage of the wardriving data captured by the ESP8266.
2.5 Arduino UNO: The Arduino UNO was employed as an additional data capture device to complement the capabilities of the ESP8266.

## 3. Methodology:
3.1 Hardware Integration:
The ESP8266 + R1 mini and associated peripherals were securely mounted onto the Mavic Pro quadcopter, ensuring stability and minimizing interference with the drone's flight dynamics. The NEO 6m GPS module was connected to the ESP8266 to provide accurate positioning information. The SD Logger mini was interfaced with the ESP8266 to record the wardriving data. Additionally, an Arduino UNO was utilized to capture data separately, enhancing the overall data collection process.

3.2 Software Implementation:
The software implementation involved programming the ESP8266 using Arduino IDE. Custom code was developed to enable the ESP8266 to scan for nearby Wi-Fi networks and record their details, including SSID, signal strength, encryption type, and channel information. The Arduino UNO was programmed to capture wardriving data independently using suitable libraries and interfaces.

## 4. Data Capture and Analysis:
4.1 Aerial Reconnaissance Flights:
The Mavic Pro quadcopter equipped with the integrated ESP8266 and GPS module was flown in the vicinity of UPES Bidholi, conducting multiple reconnaissance flights. During each flight, the ESP8266 performed wardriving scans, capturing data from the surrounding Wi-Fi networks.

4.2 Data Logging and Storage:
The captured wardriving data from the ESP8266 was logged and stored on the SD card connected to the SD Logger mini. Simultaneously, the Arduino UNO captured its own set of data for comparative analysis.

4.3 Data Analysis:
Upon completion of the reconnaissance flights, the collected wardriving data was extracted from the SD card and analyzed. Various metrics and statistics, such as network density, signal strength distribution, and encryption types, were computed

. The data captured by the Arduino UNO was also examined and compared with the ESP8266 data to validate the results.

## 5. Results and Findings:
The analysis of the wardriving data provided valuable insights into the Wi-Fi network landscape around UPES Bidholi. The results revealed the distribution of Wi-Fi networks, their signal strengths, and the prevalent encryption types. The comparative analysis between the ESP8266 and Arduino UNO data demonstrated the reliability and accuracy of the wardriving system developed.

## 6. Conclusion:
The war flight reconnaissance project successfully combined IoT technologies, UAV capabilities, and wardriving techniques to capture and analyze wardriving data from an aerial perspective. The integration of the ESP8266, Mavic Pro quadcopter, NEO 6m GPS module, SD Logger mini, and Arduino UNO facilitated the seamless execution of the project. The results obtained from the aerial reconnaissance test provided valuable information about the Wi-Fi network landscape in the vicinity of UPES Bidholi, demonstrating the effectiveness and potential of the developed system.

## 7. Future Work:
The project opens up several possibilities for future work and enhancements. Some potential areas to explore include:
- Real-time data transmission: Implementing a mechanism to transmit the wardriving data in real-time for immediate analysis and monitoring.
- Machine learning-based classification: Utilizing machine learning algorithms to classify Wi-Fi networks based on their security, type, or other attributes.
- Expanded data analysis: Conducting more comprehensive analysis of the captured wardriving data to identify trends, anomalies, and potential security vulnerabilities.

In conclusion, the war flight reconnaissance project presented an innovative approach to wardriving using UAVs and IoT technologies. The successful execution of the project demonstrated the potential of such systems for surveillance, mapping, and security applications.


## Methodology

1. Import the CSV file: Begin by importing the CSV file generated from the ESP8266 wardriving rig. This file contains the captured wardriving data, including information about the detected Wi-Fi networks. The specific method of importing the CSV file may vary depending on the programming environment or tool you are using.

2. Format and structure of the CSV file: Ensure that the CSV file follows the CSV convention and has the necessary columns containing relevant information such as the SSID (network name), signal strength, encryption type, channel information, and timestamp. This information will be crucial for analyzing the wardriving data.

3. Filtering duplicate networks: Since you mentioned that there were duplicate networks detected when the drone was sitting idle during takeoff or landing, it is important to filter out those duplicates to obtain accurate results. One way to accomplish this is by applying a time filter. By setting a specific time range, you can exclude networks captured during idle periods and focus only on the networks detected during the actual flight.

4. Applying the time filter: Identify the column in your CSV file that contains the timestamp for each captured network. This timestamp represents the exact time when each network was detected. Determine the time corresponding to the takeoff point of your drone (referred to as 'takeoff_timestamp' in the example code) and filter the data by selecting only the networks that have timestamps later than the takeoff time. This will remove the duplicate networks detected during idle periods and retain the networks captured during the flight.

5. Counting unique networks: Once you have the filtered data, you can calculate the number of unique networks detected during the flight. This can be done by counting the distinct SSID values in the filtered dataset. Each unique SSID represents a unique network.

6. Flight duration: To determine the flight time, you can calculate the difference between the maximum and minimum timestamps in the filtered dataset. This will provide an estimation of the duration of the flight during which the wardriving data was captured.

## Methodology
```bash
# import dataset

import pandas as pd
wd = pd.read_csv ('./total_data.csv', delimiter = ',')  # read warflight csv file into Pandas dataframe

print("Total WiFi AP entries: " + str(len(wd)))
wd.sample(10)  # 10 random networks
```
Your code snippet successfully imports the wardriving dataset from the "total_data.csv" file using the pandas library in Python. Let's break down the code:

1. `import pandas as pd`: This line imports the pandas library, which provides powerful data manipulation and analysis tools in Python.

2. `wd = pd.read_csv('./total_data.csv', delimiter=',')`: This line reads the CSV file named "total_data.csv" using the `read_csv()` function provided by pandas. The file path './total_data.csv' is specified, and the `delimiter=','` parameter indicates that the CSV file is comma-separated. The data is stored in a pandas DataFrame called 'wd'.

3. `print("Total WiFi AP entries: " + str(len(wd)))`: This line prints the total number of WiFi access point (AP) entries in the DataFrame 'wd'. The `len(wd)` function returns the number of rows in the DataFrame, and it is converted to a string to concatenate with the print statement.

4. `wd.sample(10)`: This line randomly samples 10 rows from the 'wd' DataFrame using the `sample()` function in pandas. It allows you to quickly inspect a subset of the data to get an idea of its structure and content.

By running this code, you will see the total number of WiFi AP entries in the dataset printed on the console. Additionally, the code will display a random sample of 10 rows from the DataFrame, providing a glimpse of the data's structure and allowing you to verify that the import was successful.

Feel free to modify or expand upon this code to perform further analysis or extract specific information from the wardriving dataset based on your project requirements.

```bash
# clean dataset by dropping excessive data entries

wd.drop(wd.index[wd["FirstSeen"] <= "8/21/2021 18:36"],0, inplace=True) # before takeoff
wd.drop(wd.index[wd["FirstSeen"] >= "8/21/2021 18:40"],0, inplace=True) # after landing

print("Total WiFi AP entries: " + str(len(wd)))
print("Unique network entries: " + str(len(wd.SSID.unique()))) 
```
In the second step of your code, you're cleaning the dataset by dropping excessive data entries based on specific time ranges. Here's a breakdown of the code:

1. `wd.drop(wd.index[wd["FirstSeen"] <= "8/21/2021 18:36"], 0, inplace=True)`: This line drops rows from the 'wd' DataFrame where the "FirstSeen" column value is less than or equal to the specified timestamp, indicating the period before takeoff. The `wd.index[wd["FirstSeen"] <= "8/21/2021 18:36"]` expression selects the indices of the rows that meet the condition, and `drop()` removes those rows. The `0` indicates that rows should be dropped, and `inplace=True` ensures the changes are applied to the DataFrame directly.

2. `wd.drop(wd.index[wd["FirstSeen"] >= "8/21/2021 18:40"], 0, inplace=True)`: Similarly, this line drops rows from the 'wd' DataFrame where the "FirstSeen" column value is greater than or equal to the specified timestamp, indicating the period after landing. It removes the rows captured after the flight. Again, the `wd.index[wd["FirstSeen"] >= "8/21/2021 18:40"]` expression selects the indices of the rows to be dropped.

3. `print("Total WiFi AP entries: " + str(len(wd)))`: This line prints the total number of WiFi AP entries remaining in the 'wd' DataFrame after dropping the excessive data entries. The `len(wd)` function returns the number of rows in the DataFrame, which is converted to a string and concatenated with the print statement.

4. `print("Unique network entries: " + str(len(wd.SSID.unique())))`: This line prints the number of unique network entries in the 'wd' DataFrame. The `wd.SSID.unique()` expression selects the unique values from the "SSID" column, and `len()` calculates the number of unique values. The result is converted to a string and concatenated with the print statement.

By running this code, you will see the updated total number of WiFi AP entries in the dataset after dropping the excessive data entries. Additionally, the code will display the number of unique network entries remaining in the DataFrame.

```bash
# plot all network entries as a cluster map w/ warflight route

import folium
from folium import FeatureGroup, LayerControl, Map, Marker
from folium.plugins import MarkerCluster

MarkerCluster()

# autofit map boundaries from dataset
wd_net_map = folium.Map(wd[['Latitude', 'Longitude']].mean().values.tolist())
wd_net_map.fit_bounds([wd[['Latitude', 'Longitude']].min().values.tolist(), wd[['Latitude', 'Longitude']].max().values.tolist()])
network_cluster = MarkerCluster().add_to(wd_net_map)

# convert dataframe to array
networks = wd.values

# warflight route
folium.PolyLine(wd[['Latitude', 'Longitude']].values.tolist(),line_opacity = 0.5, weight = 4).add_to(wd_net_map)

# cluster map of all network entries
for network in networks: folium.Marker([network[6],network[7]], popup=network[1], icon=folium.Icon(color='darkblue', icon_color='white', icon='wifi', angle=0, prefix='fa')).add_to(network_cluster)

# first and last data entry
folium.Marker([networks[0][6], networks[0][7]], popup=networks[0][3], icon=folium.Icon(color='green', icon_color='white', icon='plane', angle=0, prefix='fa')).add_to(wd_net_map)
folium.Marker([networks[len(networks)-1][6],networks[len(networks)-1][7]], popup= networks[len(networks)-1][3], icon=folium.Icon(color='red', icon_color='white', icon='plane', angle=0, prefix='fa')).add_to(wd_net_map)

display(wd_net_map)
```
The code you provided aims to plot all network entries from the wardriving dataset as a cluster map along with the warflight route using the folium library in Python. Here's an explanation of the code:

1. `MarkerCluster()`: This line initializes a MarkerCluster object to group markers together for better visualization.

2. `wd_net_map = folium.Map(wd[['Latitude', 'Longitude']].mean().values.tolist())`: This line creates a folium Map object using the mean latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame. This will serve as the base map for plotting the network entries and the warflight route.

3. `wd_net_map.fit_bounds([wd[['Latitude', 'Longitude']].min().values.tolist(), wd[['Latitude', 'Longitude']].max().values.tolist()])`: This line adjusts the map boundaries to fit the minimum and maximum latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame, ensuring that all network entries and the warflight route are visible within the map viewport.

4. `network_cluster = MarkerCluster().add_to(wd_net_map)`: This line creates a MarkerCluster object to group the network markers together. It is added to the 'wd_net_map' map object.

5. `networks = wd.values`: This line converts the 'wd' DataFrame into an array for easier iteration.

6. `folium.PolyLine(wd[['Latitude', 'Longitude']].values.tolist(), line_opacity=0.5, weight=4).add_to(wd_net_map)`: This line creates a PolyLine object using the latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame. It represents the warflight route as a line on the map.

7. `for network in networks: folium.Marker([network[6], network[7]], popup=network[1], icon=folium.Icon(color='darkblue', icon_color='white', icon='wifi', angle=0, prefix='fa')).add_to(network_cluster)`: This loop iterates over each network entry in the 'networks' array and adds a Marker object to the 'network_cluster' MarkerCluster. Each marker represents a network entry with the latitude and longitude coordinates, a popup displaying the network name (network[1]), and a wifi icon.

8. `folium.Marker([networks[0][6], networks[0][7]], popup=networks[0][3], icon=folium.Icon(color='green', icon_color='white', icon='plane', angle=0, prefix='fa')).add_to(wd_net_map)`: This line adds a marker to the 'wd_net_map' representing the first data entry in the 'networks' array. It has a green airplane icon and displays the corresponding popup.

9. `folium.Marker([networks[len(networks)-1][6], networks[len(networks)-1][7]], popup=networks[len(networks)-1][3], icon=folium.Icon(color='red', icon_color='white', icon='plane', angle=0, prefix='fa')).add_to(wd_net_map)`: This line adds a marker to the 'wd_net_map' representing the last data entry in the 'networks' array. It has a red airplane icon and displays the corresponding popup.

10. `display(wd_net_map)`: This line displays the final map, including the network markers, warflight route, and the first and last data entry markers.

By running this code, you should see a cluster map with network markers plotted along with the warflight route. The first and last data entries will be marked with airplane icons

```bash
# network concentration heat map + known device location

known_devices = ["Target3", "Bingus Mobile"]

import folium, numpy
from folium import Map, Marker, plugins

# autofit map boundaries from dataset
wd_heat_map = folium.Map(wd[['Latitude', 'Longitude']].mean().values.tolist())
wd_heat_map.fit_bounds([wd[['Latitude', 'Longitude']].min().values.tolist(), wd[['Latitude', 'Longitude']].max().values.tolist()])

for device in wd.loc[wd["SSID"].isin(known_devices)].values:
  folium.Marker( location=[device[6], device[7]], popup=device[1], icon=folium.Icon(color="darkblue",icon='wifi',prefix='fa')).add_to(wd_heat_map)

wd_heat_map.add_child(plugins.HeatMap(wd[['Latitude', 'Longitude']].to_numpy(), radius=30))
```
In the code snippet you provided, you are generating a network concentration heat map along with markers representing the location of known devices. Here's an explanation of the code:

1. `known_devices = ["Target3", "Bingus Mobile"]`: This line defines a list of known devices by specifying their SSID values. Modify this list to include the SSID names of the devices you want to mark on the map.

2. `wd_heat_map = folium.Map(wd[['Latitude', 'Longitude']].mean().values.tolist())`: This line creates a folium Map object called 'wd_heat_map' using the mean latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame. This will serve as the base map for plotting the heat map and markers.

3. `wd_heat_map.fit_bounds([wd[['Latitude', 'Longitude']].min().values.tolist(), wd[['Latitude', 'Longitude']].max().values.tolist()])`: This line adjusts the map boundaries to fit the minimum and maximum latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame, ensuring that all data points are visible within the map viewport.

4. `for device in wd.loc[wd["SSID"].isin(known_devices)].values: folium.Marker(location=[device[6], device[7]], popup=device[1], icon=folium.Icon(color="darkblue", icon='wifi', prefix='fa')).add_to(wd_heat_map)`: This loop iterates over the rows of the 'wd' DataFrame where the 'SSID' value is present in the 'known_devices' list. It adds a Marker object to the 'wd_heat_map' for each known device location, using the latitude and longitude values from the corresponding columns of the DataFrame. Each marker has a popup displaying the SSID value (device[1]) and is styled with a dark blue wifi icon.

5. `wd_heat_map.add_child(plugins.HeatMap(wd[['Latitude', 'Longitude']].to_numpy(), radius=30))`: This line adds a HeatMap layer to the 'wd_heat_map' using the latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame. The `to_numpy()` function converts these columns into a NumPy array, and the `radius` parameter sets the radius of influence for each data point in the heat map.

By running this code, you will see a map with a network concentration heat map overlaid and markers representing the locations of the known devices. The heat map will visualize the density of network entries, and the markers will highlight the positions of the known devices.

```bash
import folium
from folium import FeatureGroup, LayerControl, Map, Marker

wd_encryption_map = folium.Map(wd[['Latitude', 'Longitude']].mean().values.tolist())
wd_encryption_map.fit_bounds([wd[['Latitude', 'Longitude']].min().values.tolist(), wd[['Latitude', 'Longitude']].max().values.tolist()])

# map feature groups for different encryption types
wep_feature_group = folium.FeatureGroup("WEP")
wpa_feature_group = folium.FeatureGroup("WPA")
wpa2_feature_group = folium.FeatureGroup("WPA2")
opn_feature_group = folium.FeatureGroup("Open")
none_feature_group = folium.FeatureGroup("None")

# convert dataframe to array
networks = wd.values

# add network coordinates
for network in networks:
  if   (network[2] == "[WPA-PSK-CCMP+TKIP][ESS]"):
    folium.Marker(location=[network[6],network[7]],  popup=network[1], icon=folium.Icon(color="blue",icon='user-secret',prefix='fa')).add_to(wpa_feature_group)

  elif (network[2] == "[WPA2-PSK-CCMP+TKIP][ESS]"):
    folium.Marker(location=[network[6],network[7]],  popup=network[1], icon=folium.Icon(color="green",icon='user-secret',prefix='fa')).add_to(wpa2_feature_group)

  elif (network[2] == "[WEP][ESS]"):
    folium.Marker(location=[network[6],network[7]],  popup=network[1], icon=folium.Icon(color="red",icon='user-secret',prefix='fa')).add_to(wep_feature_group)

  elif (network[2] == "[ESS]"):
    folium.Marker(location=[network[6],network[7]],  popup=network[1], icon=folium.Icon(color="orange",icon='user-secret',prefix='fa')).add_to(opn_feature_group)

  elif (network[2] == "[WPA-PSK-CCMP+TKIP][WPA2-PSK-CCMP+TKIP][ESS]"):
    folium.Marker(location=[network[6],network[7]],  popup=network[1], icon=folium.Icon(color="purple",icon='user-secret',prefix='fa')).add_to(none_feature_group)

# add feature groups to map 
wep_feature_group.add_to(wd_encryption_map)
wpa_feature_group.add_to(wd_encryption_map)
wpa2_feature_group.add_to(wd_encryption_map)
opn_feature_group.add_to(wd_encryption_map)
none_feature_group.add_to(wd_encryption_map)

folium.LayerControl().add_to(wd_encryption_map)

display(wd_encryption_map)
```
The code provided is generating a map that visualizes different Wi-Fi network encryption types using markers. Here's an explanation of the code:

1. `wd_encryption_map = folium.Map(wd[['Latitude', 'Longitude']].mean().values.tolist())`: This line creates a folium Map object called 'wd_encryption_map' using the mean latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame. The map will be centered around the mean coordinates of the network entries.

2. `wd_encryption_map.fit_bounds([wd[['Latitude', 'Longitude']].min().values.tolist(), wd[['Latitude', 'Longitude']].max().values.tolist()])`: This line adjusts the map boundaries to fit the minimum and maximum latitude and longitude values from the 'Latitude' and 'Longitude' columns of the 'wd' DataFrame, ensuring that all data points are visible within the map viewport.

3. Map feature groups: Feature groups are created to group markers based on different encryption types. There are feature groups for WEP, WPA, WPA2, Open, and None.

4. Loop over network entries: The code then iterates over each network entry in the 'wd' DataFrame.

5. Markers for different encryption types: Based on the encryption type ('network[2]'), the code adds markers to the corresponding feature group. Each marker is placed at the coordinates (latitude and longitude) of the network entry and is styled with a different color and a user-secret icon (representing the encryption type).

6. Adding feature groups to the map: After adding the markers to their respective feature groups, the feature groups are added to the 'wd_encryption_map'.

7. Layer control: The folium.LayerControl() function is used to add a control panel to the map, allowing users to toggle the display of different feature groups.

8. Display the map: The 'wd_encryption_map' is displayed using the 'display()' function.

When you run this code, you will see a map with markers representing Wi-Fi networks, grouped by encryption type. Each marker's color and icon indicate the encryption type of the network. The layer control panel allows you to toggle the display of different encryption types on the map.

## Reference
https://github.com/AlexLynd/ESP8266-Wardriving/blob/master/JN-Scripts/Missoula-Warflight-08-21-2021.ipynb

https://colab.research.google.com/github/AlexLynd/ESP8266-Wardriving/blob/master/JN-Scripts/Missoula-Warflight-08-21-2021.ipynb#scrollTo=ckCcIv_FRfzT

