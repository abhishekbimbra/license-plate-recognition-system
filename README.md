# License Plate Recognition System

This project is a real-time License Plate Recognition (LPR) system that detects and reads license plate numbers from video input using YOLOv10 for object detection and PaddleOCR for optical character recognition (OCR). Extracted plate numbers are automatically stored in both JSON files and an SQLite database for persistent storage.

---

## 🔍 Features

- 🎯 Real-time license plate detection using YOLOv10
- 🔠 Text recognition using PaddleOCR
- 🧾 Data logging every 20 seconds in JSON format
- 🗃️ SQLite database integration for structured storage
- 🎥 Frame-by-frame processing with live display

---

## 🧰 Technologies Used

- Python
- OpenCV
- YOLOv10 (Ultralytics)
- PaddleOCR
- SQLite
- NumPy, Regex
- JSON

---

## 📂 Project Structure

├── data/ # Input videos
├── weights/ # YOLOv10 trained weights (best.pt)
├── json/ # Output JSON logs
├── licensePlatesDatabase.db # SQLite database (auto-generated)
├── main.py # Main processing script
├── db_setup.py # SQLite table creation script
├── README.md # Project documentation



---

## ⚙️ How It Works

1. Loads video from the `data/` directory.
2. YOLOv10 detects license plates in frames.
3. PaddleOCR extracts text from detected plates.
4. Every 20 seconds, plate numbers are:
   - Logged in a timestamped JSON file
   - Stored in an SQLite database with start and end times
5. Video frame is displayed with annotated detection boxes and text.

---
## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/License-Plate-Recognition.git
cd "License-Plate-Recognition"
```

---

### 2. Install Dependencies

```bash
Copy
Edit
pip install -r requirements.txt
```
Make sure to install PaddleOCR and Ultralytics YOLOv10:

```bash
pip install paddleocr
pip install ultralytics
```
### 3. Add YOLO Weights
Place your trained YOLOv10 weights (e.g., best.pt) inside the weights/ directory.
### 4. Set Up the SQLite Database
```bash
python db_setup.py
```
### 5. Run the Main Application
```bash
python main.py
```
## 📝 Output
Example JSON Log
```json
{
  "Start Time": "2025-06-10T15:30:10",
  "End Time": "2025-06-10T15:30:30",
  "License Plate": ["KA01AB1234", "DL03CD5678"]
}
```
## Example SQLite Table Structure
| id | start\_time         | end\_time           | license\_plate |
| -- | ------------------- | ------------------- | -------------- |
| 1  | 2025-06-10T15:30:10 | 2025-06-10T15:30:30 | KA01AB1234     |

## 👤 Author
#### Abhishek Bimbra

## 📜 License
This project is open-source and available under the MIT License.
