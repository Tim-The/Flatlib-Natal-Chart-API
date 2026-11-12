# Flatlib Natal Chart API – README (English translation)

Translated from the Russian add-on README. Source: `navi-vonamut/Flatlib-Natal-Chart-API`.

## Overview

A local Home Assistant add-on that provides a high-performance HTTP API for advanced astrological calculations using [Flatlib](https://github.com/flatangle/flatlib).

## ✨ Update to version v0.2.0

- **Switch to FastAPI:** The server backend was completely rewritten from Flask to **FastAPI**, which significantly improves performance and stability.
- **Extended capabilities:** Added new endpoints for calculating daily, monthly and yearly predictions, as well as synastry.

## 📄 Description

This add-on runs a high-performance **FastAPI server** locally in your Home Assistant environment. It serves as a powerful backend for complex astrological computations, offering a fast and reliable API. All calculations are done locally, which keeps your data **private**.

The add-on is intended for **integration with other Home Assistant components**, such as automations, sensors and scripts, and for passing structured data to LLMs (Large Language Models) for personalized interpretations.

## 🔮 Features

- **Natal chart calculation:** Full calculation of planet positions, angles (Asc, MC), house cusps, lunar nodes, Lilith (Syzygy) and the Part of Fortune.
- **Aspect calculation:** Determination of natal aspects.
- **Daily, monthly and yearly predictions:** New endpoints for calculating transits and predictions for specific periods.
- **Synastry calculation:** New endpoint for analyzing the compatibility of two natal charts.
- **JSON output:** Data is provided in a convenient JSON format, ready for processing in Home Assistant or passing to an LLM.

## 🛠️ Configuration

After installing the add-on, go to the **"Configuration"** tab in the user interface.

- **`log_level` (Logging level):** Sets how detailed the add-on's logs are. `info` is recommended for normal operation. Use `debug` for troubleshooting.

## 💡 Using the API

The server is available at `http://a0d7b954-flatlib-server:8080`. To access it from outside Home Assistant, set up port forwarding in the add-on configuration.

### Main endpoints

- **`/natal` (POST):** Calculates a natal chart.
- **`/predict/daily` (POST):** Daily predictions.
- **`/predict/monthly` (POST):** Monthly predictions.
- **`/predict/yearly` (POST):** Yearly predictions.
- **`/synastry` (POST):** Calculates synastry.
- **`/health` (GET):** Checks that the API is running.

Detailed request and response examples for all endpoints are in the repository's main [README](https://github.com/navi-vonamut/Flatlib-Natal-Chart-API/blob/main/README.md).

## ❓ Support and feedback

If you have questions or problems, please open an [Issue in the main GitHub repository](https://github.com/navi-vonamut/Flatlib-Natal-Chart-API/issues).

## 📄 License

This add-on is distributed under the [MIT License](https://github.com/navi-vonamut/Flatlib-Natal-Chart-API/blob/main/LICENSE).

## Note on your setup

The README says the add-on is reached at `http://a0d7b954-flatlib-server:8080`, but the integration's `api.py` uses `http://localhost:8080`. If the integration can't reach the add-on, that hostname is where to look.

