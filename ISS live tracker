import requests
import time

# API Endpoint URL (Where the live iss-now.json data comes from)
url = "http://api.open-notify.org/iss-now.json"

print("--- ISS Live Tracker Has Started (Infinite Loop) ---")
print("Press Ctrl+C in the terminal if you want to stop it.\n")

counter = 1

# Using 'while True' so the script keeps running continuously in the background
while True:
    try:
        response = requests.get(url)
        
        # Check if the connection to the API was successful (Status Code 200)
        if response.status_code == 200:
            data = response.json()
            
            # Extracting the required values from the JSON data
            latitude = data["iss_position"]["latitude"]
            longitude = data["iss_position"]["longitude"]
            
            # Displaying the clean, formatted data on the screen
            print(f"[Check {counter}] ISS Live Location:")
            print(f"-> Latitude: {latitude}")
            print(f"-> Longitude: {longitude}")
            print("-" * 30)
            
            counter += 1
        else:
            print(f"Error: Unable to connect. Status Code: {response.status_code}")
            
    except Exception as e:
        print(f"An error occurred: {e}")
        
    # Wait for 10 seconds before fetching the next live location
    time.sleep(10)
