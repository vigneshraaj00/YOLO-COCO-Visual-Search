# YOLO-COCO-Visual-Search
# 🔎 YOLO11 Image Search Engine

An AI-powered image search application built with **YOLO11**, **PyTorch**, and **Streamlit**.  
The application detects objects in images and allows users to search for images based on detected object classes.

## Abstract / Introduction

The YOLO11 Image Search Engine is a computer vision application designed to search and retrieve images based on the objects present in them. Traditional image searching requires users to manually inspect large collections of images, which can be time-consuming.

This project uses the YOLO11 object detection model to identify objects present in images. The detected object classes are stored as metadata and can later be used to search for images containing specific objects.

A Streamlit-based web interface provides an interactive way for users to search images and view the detection results. The project also supports GPU acceleration using NVIDIA CUDA when compatible hardware is available.

The system demonstrates the practical application of deep learning, object detection, image retrieval, and web-based AI deployment.

## Dataset & YOLO Model Details
Dataset

The project uses the COCO (Common Objects in Context) dataset for object detection and image search.

COCO contains images representing common objects from real-world scenes and provides annotations for multiple object categories.

Examples of object classes include:

Person
Car
Bicycle
Dog
Cat
Chair
Laptop
Bottle
Bus
Motorcycle

The COCO dataset is used as the source of images for testing and demonstrating the image search system.

Dataset Structure
data/
└── raw/
    └── coco-val-2017-500/
        ├── 00000000139.jpg
        ├── 00000000802.jpg
        ├── ...

Note: The dataset is not uploaded to GitHub because of its large size. It should be downloaded separately and placed in the required directory.

YOLO11 Model

The project uses YOLO11 for object detection.

YOLO (You Only Look Once) is a real-time object detection architecture that can identify objects and their locations within an image.

The model performs:

Input Image
     ↓
YOLO11 Model
     ↓
Object Detection
     ↓
Bounding Boxes + Class Labels + Confidence

The detected information is then used by the image-search system.

Example:

Image
 ↓
YOLO11
 ↓
Person – 0.94
Car – 0.87
Dog – 0.81
##  Environment Setup
Requirements

The project requires:

Python 3.x
Conda / Anaconda
PyTorch
Ultralytics YOLO
OpenCV
NumPy
Pillow
Streamlit
PyYAML
Clone the Repository
git clone https://github.com/vigneshraaj00/YOLO-COCO-Visual-Search.git
cd YOLOV11-Search-App
Create Conda Environment
conda create -n yolo_image_search python=3.11

Activate the environment:

conda activate yolo_image_search

Install the project dependencies:

pip install -r requirements.txt
## GPU Installation / CPU Installation
GPU Installation

If an NVIDIA GPU is available, GPU acceleration can be used for faster YOLO inference.

Check whether NVIDIA drivers are detected:

nvidia-smi

Verify PyTorch CUDA support:

python -c "import torch; print(torch.cuda.is_available())"

If the output is:

True

PyTorch can access the NVIDIA GPU.

Check the GPU name:

python -c "import torch; print(torch.cuda.get_device_name(0))"

The YOLO model can then perform inference using the GPU.

CPU Installation

If an NVIDIA GPU is not available, the application can run using the CPU.

Verify:

python -c "import torch; print(torch.cuda.is_available())"

Expected output:

False

The application can still perform object detection, although CPU inference may be slower than GPU inference.

## How to Run in VS Code Using Conda
Step 1 — Open the project

Open the project folder in Visual Studio Code.

Step 2 — Open the terminal

Use:

Terminal → New Terminal
Step 3 — Activate the Conda environment
conda activate yolo_image_search
Step 4 — Verify Python
python --version
Step 5 — Verify Streamlit
python -m streamlit --version
Step 6 — Run the application
python -m streamlit run app.py

The application will be available at:

http://localhost:8501
VS Code Workflow
VS Code
   ↓
Conda Environment
   ↓
Python
   ↓
YOLO11
   ↓
Streamlit
   ↓
Image Search Application
## How to Deploy Using Streamlit

The application can be deployed using Streamlit Community Cloud.

Step 1

Push the project to GitHub.

Step 2

Open Streamlit Community Cloud and sign in using GitHub.

Step 3

Create a new application.

Select:

Repository:
Yaazhi1401/YOLOV11-Search-App

Select the main branch:

main

Select the application file:

app.py
Step 4

Deploy the application.

Streamlit will install the dependencies specified in:

requirements.txt

and start the application.

Deployment Flow
GitHub Repository
       ↓
Streamlit Community Cloud
       ↓
requirements.txt
       ↓
app.py
       ↓
YOLO11 Image Search Engine
       ↓
Live Web Application

Deployment Note: Large COCO datasets and model weights should not be stored directly in the GitHub repository. For cloud deployment, the application should use downloadable model weights and/or user-uploaded images.

8. Output Screenshots

Screenshots should be added to demonstrate the working application.

8.1 Streamlit UI

<img width="1231" height="1278" alt="ChatGPT Image Sep 21, 2026, 07_58_08 PM" src="https://github.com/user-attachments/assets/8faf8b33-da80-467e-abce-d2f0b80264af" />


8.2 YOLO Detection Output

<img width="1886" height="982" alt="image" src="https://github.com/user-attachments/assets/733e3021-61d5-4fe0-bb20-b38bdae03df5" />
<img width="1877" height="1023" alt="image" src="https://github.com/user-attachments/assets/d4e341b1-f5ea-440f-957a-3e5304c0acf0" />



## Enhancements / Innovations Added

The following enhancements were added to improve the basic YOLO object detection workflow:

🔎 Object-Based Image Search

Instead of simply detecting objects, the detected classes are used to retrieve relevant images.

🖥️ Interactive Streamlit Interface

A web-based interface allows users to interact with the image-search system without writing Python code.

⚙️ Configurable Architecture

Configuration values are separated from the main application logic using a configuration file.

🧩 Modular Project Structure

The application separates configuration, inference, and utility functions into different modules.

src/
├── config.py
├── inference.py
└── utils.py
🚀 GPU Acceleration

The system can utilize NVIDIA CUDA-enabled GPUs for faster object detection when available.

📊 Detection Metadata

Object detection results can be stored as metadata and used for image retrieval.

🔮 Future Innovation

The system can be extended with:

Natural-language image search
Image embeddings
Vector databases
Semantic search
Image similarity ranking
User image upload
Cloud deployment
## Results & Conclusion
Results

The YOLO11 Image Search Engine successfully demonstrates how object detection can be combined with image retrieval.

The system:

Detects objects using YOLO11.
Identifies object classes in images.
Stores detection information as metadata.
Searches images based on detected objects.
Displays matching images through a Streamlit interface.
Supports GPU acceleration when available.

The project provides an interactive approach to searching image collections using detected visual content instead of manually browsing through images.

Conclusion

The YOLO11 Image Search Engine demonstrates the practical integration of deep learning and web technologies to build an intelligent image retrieval system.

By combining YOLO11 object detection, PyTorch, Python, and Streamlit, the project transforms object-detection results into a searchable image collection.

The modular architecture also makes the system suitable for future improvements such as semantic search, image embeddings, vector databases, natural-language queries, and cloud deployment.

Overall, the project provides a practical demonstration of computer vision, deep learning, object detection, image retrieval, and AI application deployment.


Technologies: Python • YOLO11 • PyTorch • Streamlit • OpenCV • Computer Visiont included in this repository.

Download the required YOLO11 weights and place them in the location specified by the project configuration.
