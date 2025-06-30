# Solarclock

Finding out the geopositions with solar clock.



🌞 SolarClock - Sunrise \& Sunset Tracker

SolarClock is a Python application that calculates the sunrise and sunset times for any given location using latitude and longitude. It's designed to help users understand daylight duration and optimize their schedules accordingly.



🚀 Features

🌍 Accepts user input (latitude \& longitude) or detects location automatically



🕰️ Displays local sunrise and sunset times



📆 Uses current system date (can be customized)



🧭 Optional: Converts coordinates to location name



🐍 Built using Python libraries: astral, geopy, and datetime



🛠️ Installation

bash

Copy

Edit

git clone https://github.com/yourusername/solarclock.git

cd solarclock

pip install -r requirements.txt

Required Libraries:



astral



geopy



datetime (built-in)



Install them with:



bash

Copy

Edit

pip install astral geopy

🧪 Usage

python

Copy

Edit

python solarclock.py

You can also use it as a module and pass latitude \& longitude:



python

Copy

Edit

from solarclock import get\_sun\_times



sunrise, sunset = get\_sun\_times(latitude=25.2048, longitude=55.2708)  # Dubai coords

print("Sunrise:", sunrise)

print("Sunset:", sunset)

📷 Sample Output

yaml

Copy

Edit

📍 Location: Dubai, United Arab Emirates

📅 Date: 2025-06-30

🌅 Sunrise: 05:32 AM

🌇 Sunset : 07:15 PM

💡 How It Works

Uses Astral to compute sun positions based on geographic coordinates



Optionally integrates geopy to reverse geocode the coordinates into city names



Great for location-aware solar planning, automation scripts, or education





