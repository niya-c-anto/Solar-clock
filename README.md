# 🌞 Solar Clock App

The **Solar Clock App** is a web-based tool built using Flask that provides detailed solar information, Islamic prayer (Niskar) times, and moon phases based on a user's location. It features a dynamic light/dark theme, interactive map, date selection, and downloadable summaries — all accessible via a friendly tabbed interface.

---

## 🔧 Features

- 🌅 **Sunrise, Sunset, Solar Noon, and Daylight Duration**
- 🕌 **Islamic Prayer (Niskar) Times**
- 🌙 **Moon Phase with Emoji**
- 🗺️ **Interactive Map View of the Selected Location**
- 🌓 **Light/Dark Theme Based on Solar Time**
- 📅 **Date Picker to See Future or Past Data**
- 📤 **Download and Export Button for Solar Info Summary**

---

## 🚀 Tech Stack

| Tech | Purpose |
|------|---------|
| Flask | Backend Web Framework |
| HTML/CSS/JS | Frontend User Interface |
| Leaflet.js | Interactive Mapping |
| Astral | Compute sunrise/sunset and other solar data |
| Ephem | Moon phase calculation |
| Geopy + Nominatim | Geolocation from place name |
| Pyngrok | Publicly expose Flask app in Google Colab or locally |

---

## 📦 Installation

```bash
pip install flask pyngrok astral geopy ephem
```

---

## 🌐 How to Run (in Google Colab or locally)

1. **Paste your ngrok token** in the code where mentioned:
   ```python
   ngrok.set_auth_token("PASTE_YOUR_NGROK_TOKEN")
   ```

2. **Run the app**:
   ```python
   public_url = ngrok.connect(5000)
   print("🚀 App running at:", public_url)
   app.run(port=5000)
   ```

3. **Open the printed `public_url`** in your browser to access the app.

---

## 🧠 How It Works

### 1. **User Input**
- User enters a location (e.g., "Kochi, India") and selects a date.
- A POST request is triggered.

### 2. **Geolocation**
- The `geopy` library queries Nominatim (OpenStreetMap) to convert the location string into latitude and longitude.

### 3. **Solar Calculations**
- The `astral` library calculates:
  - 🌅 Sunrise
  - 🌇 Sunset
  - 🌞 Solar Noon
  - 🕗 Daylight Duration

### 4. **Progress Bar**
- The app compares the current time with sunrise/sunset to show a symbolic day progress bar:
  - Example: `🌅||||☀️------🌇`

### 5. **Dynamic Theme**
- If current time is before sunrise or after sunset, the theme switches to dark mode.

### 6. **Moon Phase**
- Uses `ephem` to calculate the moon phase as a percentage.
- A corresponding emoji is displayed:
  - 🌑, 🌒, 🌓, 🌔, 🌕, etc.

### 7. **Niskar Timings**
- Approximated based on solar events:
  - Fajr = 1 hour before sunrise
  - Dhuhr = Solar Noon
  - Asr = 3 hours after Dhuhr
  - Maghrib = Sunset
  - Isha = 2 hours after Sunset

### 8. **Interactive Map**
- Leaflet.js shows the selected location with a zoomed-in map and marker.

### 9. **Export Button**
- Allows downloading a `.txt` file with the solar and moon info for the chosen location and date.

---

## 📁 Folder Structure (if applicable)

```
solar-clock/
│
├── app.py              # Main Flask application
├── templates/
│   └── index.html      # Rendered via render_template_string (inline)
├── README.md           # This file
└── requirements.txt    # Python packages
```

---

## 🧪 Sample Output

```
Location: Kochi, India
Date: 2025-07-05

Sunrise: 06:10 AM
Noon:    12:25 PM
Sunset:  06:40 PM
Daylight: 12h 30m

Moon Phase: 🌔 62.4%

Niskar Times:
Fajr:    05:10 AM
Dhuhr:   12:25 PM
Asr:     03:25 PM
Maghrib: 06:40 PM
Isha:    08:40 PM
```


