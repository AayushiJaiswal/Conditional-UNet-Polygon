# Conditional-UNet-Polygon

🖌️ PolygonColorFiller
A deep learning project that uses a Conditional U-Net model to fill polygons with specified colors. Given an input polygon image and a target color, the model learns to generate a filled version of the polygon in that color.

📌 Project Description
This project demonstrates the use of a U-Net-based image-to-image translation model conditioned on color inputs. The model takes:

🖼️ An input polygon shape image (e.g., triangle, hexagon)

🎨 A target color name (e.g., "red", "blue")

and generates:

🧾 A color-filled polygon image as output.

It uses embeddings to represent colors and combines them with image features during training.

🧠 Model Architecture
Base Model: U-Net (encoder-decoder)

Conditional Input: Color embeddings

Loss Function: MSE (Mean Squared Error)

Optimizer: Adam

Color embeddings are injected at the bottleneck of the U-Net to condition the output image generation.

📁 Dataset Structure
The dataset should be organized as follows:

kotlin
Copy
Edit
data/
├── train.json
├── val.json
├── inputs/
│   ├── triangle.png
│   ├── hexagon.png
│   └── ...
└── outputs/
    ├── red_triangle.png
    ├── blue_hexagon.png
    └── ...
Each entry in train.json or val.json should follow this format:

json
Copy
Edit
{
  "input_polygon": "triangle.png",
  "colour": "red",
  "output_image": "red_triangle.png"
}
🚀 How to Run (Google Colab)
Clone the repository or open in Google Colab

Upload dataset files (inputs, outputs, train.json, val.json)

Train the model:

python
Copy
Edit
python train.py  # (Or run the training cell in Colab)
Test on new polygon + color:

python
Copy
Edit
model.predict(polygon_img, color="green")
🧪 Sample Outputs
Input Polygon	Color	Output
Triangle	Red	
Hexagon	Blue	

🔧 Tech Stack
Python 🐍

PyTorch 🔥

Google Colab

JSON for metadata

Matplotlib/OpenCV for image loading

📈 Future Work
Add support for gradients/multi-color fills

Use diffusion/attention-based models for complex patterns

Deploy with Streamlit for interactive usage

🙋‍♀️ Maintainer
Aayushi Jaiswal
BTech, JSS Academy of Technical Education
LinkedIn | GitHub | Portfolio
