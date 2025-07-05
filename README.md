**🌞 Solar Clock App**

The Solar Clock App is a web-based tool built using Flask that provides detailed solar information, Islamic prayer (Niskar) times, and moon phases based on a user's location. It features a dynamic light/dark theme, interactive map, date selection, and downloadable summaries — all accessible via a friendly tabbed interface.



**🔧 Features**

🌅 Sunrise, Sunset, Solar Noon, and Daylight Duration



🕌 Islamic Prayer (Niskar) Times



🌙 Moon Phase with Emoji



🗺️ Interactive Map View of the Selected Location



🌓 Light/Dark Theme Based on Solar Time



📅 Date Picker to See Future or Past Data



📤 Download and Export Button for Solar Info Summary



**🚀 Tech Stack**

| Tech              | Purpose                                              |

| ----------------- | ---------------------------------------------------- |

| Flask             | Backend Web Framework                                |

| HTML/CSS/JS       | Frontend User Interface                              |

| Leaflet.js        | Interactive Mapping                                  |

| Astral            | Compute sunrise/sunset and other solar data          |

| Ephem             | Moon phase calculation                               |

| Geopy + Nominatim | Geolocation from place name                          |

| Pyngrok           | Publicly expose Flask app in Google Colab or locally |





**📦 Installation**

pip install flask pyngrok astral geopy ephem

🌐 How to Run (in Google Colab or locally)

Paste your ngrok token

ngrok.set\_auth\_token("PASTE\_YOUR\_NGROK\_TOKEN")

Run the app:



public\_url = ngrok.connect(5000)

print("🚀 App running at:", public\_url)

app.run(port=5000)

Open the printed public\_url in your browser to access the app.



**🧠 How It Works**

1\. User Input

User enters a location (e.g., "Kochi, India") and selects a date.



A POST request is triggered.



2\. Geolocation

The geopy library queries Nominatim (OpenStreetMap) to convert the location string into latitude and longitude.



3\. Solar Calculations

The astral library calculates:



🌅 Sunrise



🌇 Sunset



🌞 Solar Noon



🕗 Daylight Duration



4\. Progress Bar

The app compares the current time with sunrise/sunset to show a symbolic day progress bar:



Example: 🌅||||☀️------🌇



5\. Dynamic Theme

If current time is before sunrise or after sunset, the theme switches to dark mode.



6\. Moon Phase

Uses ephem to calculate the moon phase as a percentage.



A corresponding emoji is displayed:



🌑, 🌒, 🌓, 🌔, 🌕, etc.



7\. Niskar Timings

Approximated based on solar events:



Fajr = 1 hour before sunrise



Dhuhr = Solar Noon



Asr = 3 hours after Dhuhr



Maghrib = Sunset



Isha = 2 hours after Sunset



8\. Interactive Map

Leaflet.js shows the selected location with a zoomed-in map and marker.



9\. Export Button

Allows downloading a .txt file with the solar and moon info for the chosen location and date.

