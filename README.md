# Vision-Object-Search-App-YOLOv11-Streamlit

A Computer Vision Search Engine using YOLOv11 for object detection and Streamlit for web-based interactive visual search.
Search and filter objects in batches of images, customize grid display, and analyze detections—all from an easy-to-use browser interface.

# 🚀 Features
Object detection with fast YOLOv11 model weights

Streamlit-powered web app UI for visual exploration

Batch image folder processing for inference

Search and filter images by object class, count, AND/OR rules

Real-time display with customizable grid of results

Export metadata and search results to JSON

# 📦 Installation Guide
## Step 1: Clone the Repository
```
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```
## Step 2: Create Environment (GPU Recommended)
```
conda create -n yolo_image_search_gpu python=3.11 -y
conda activate yolo_image_search_gpu
conda install pytorch==2.5.1 torchvision==0.20.1 pytorch-cuda=12.4 -c pytorch -c nvidia
pip install -r requirements.txt

```
(For CPU only, omit the CUDA install lines above.)


## ⚡ Usage
1. Place your YOLOv11 weights (e.g. yolo11m.pt) in the project folder.

2. Put your test images in a folder (e.g. test_images/).

3. Run the Streamlit app:

```
streamlit run app.py
```
4. Interact in your browser:

  Choose “Process new images” to batch run detection.

  Set image folder and weights path, then click Start Inference.

  Use the search/search filters and grid controls to analyze results.

  Download processed metadata or search outcomes as JSON.

## 🖼️ Output Example
Below: Sample input and detection outputs (red bounding boxes for detected objects):

<img width="1912" height="928" alt="SS1" src="https://github.com/user-attachments/assets/6180029f-3a9d-40dc-a1f6-a012971f070f" />

<img width="1907" height="918" alt="SS2" src="https://github.com/user-attachments/assets/b81715b2-4d2b-46d8-8c1a-541c1fedaebe" />

<img width="1897" height="910" alt="SS3" src="https://github.com/user-attachments/assets/ee0b2857-11cb-45b6-b7a1-0ae2e1d31b23" />

<img width="1913" height="916" alt="SS4" src="https://github.com/user-attachments/assets/03ff8989-e9c4-41f0-abfa-f191412aabb9" />

<img width="1917" height="921" alt="SS5" src="https://github.com/user-attachments/assets/c04c54ca-e73e-4c89-a9e9-acf92c2f4c03" />





## 🛠️ Code Structure
app.py : Streamlit user interface & logic

src/inference.py : Model loading, running detection

src/utils.py : Metadata, visualization, helper functions

configs/ : Config files (YAML, weights)

test_images/ : Example/test batch folder

## ✏️ Customization
Change box color:
In app.py (results display section), edit:

```python
color = "#FF4B4B"  # Red bounding box (editable)
```
Search filter logic:
Use controls for “Any” (OR) or “All” (AND) queries on object classes.

Export:
Download results directly in-app as JSON.

## 🤔 Troubleshooting
“Processed 0 images”: Check “image directory path” points to a valid folder of .jpg/.png images.

“Config not found”: Ensure you have the required YAML and JSON files.

Streamlit errors: Confirm all required packages via pip install -r requirements.txt.

## 📄 License
MIT License
