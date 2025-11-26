# resizertool
🖼️ Image Resizer Tool

A lightweight Python tool to resize and convert images in bulk using Pillow.
This script helps automate repetitive image processing tasks—perfect for web optimization, batch editing, and workflow automation.

📌 Objective

Resize all images in a folder and optionally convert them to another format.

🛠️ Tools Used

Python

Pillow (PIL)

os module

📂 How It Works

Reads all images from the input folder using os

Resizes each image with Pillow

Saves output images to a new folder

(Optional) Converts image format (e.g., JPG → PNG)

📁 Project Structure
ImageResizer/
│── images/        # Input folder (your images go here)
│── output/        # Auto-generated output folder
│── resize.py      # Main resizing script
└── README.md

🔧 Installation

Install Pillow:

pip install pillow

▶️ Usage

Put your images inside the images/ folder

Open resize.py and configure:

input_folder = "images"
output_folder = "output"
new_size = (800, 800)  # (width, height)
output_format = "JPEG"  # PNG, JPEG, WEBP, etc.


Run the script:

python resize.py


Resized images will be saved in the output/ folder.

📘 Example Code (resize.py)
import os
from PIL import Image

input_folder = "images"
output_folder = "output"
new_size = (800, 800)
output_format = "JPEG"

if not os.path.exists(output_folder):
    os.makedirs(output_folder)

for filename in os.listdir(input_folder):
    if filename.lower().endswith((".png", ".jpg", ".jpeg", ".webp")):
        img_path = os.path.join(input_folder, filename)
        img = Image.open(img_path)

        img = img.resize(new_size)

        new_filename = os.path.splitext(filename)[0] + "." + output_format.lower()
        save_path = os.path.join(output_folder, new_filename)

        img.save(save_path, output_format)

print("All images resized successfully!")

✅ Outcome

A fully automated image-resizing tool that processes entire folders in seconds—ideal for bulk image tasks.
