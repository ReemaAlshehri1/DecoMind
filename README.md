# DecoMind 
A Generative AI System for Personalized Interior Design Layouts


This system is designed to support individuals who cannot afford professional interior designers by providing automated, personalized room designs tailored to their preferences and spatial layout.

---

##  How It Works

1. It takes user inputs:
   - Room type  
   - Room style  
   - Room dimensions  
   - Window and door positions  
   - Types of furniture from the desired store

2. Using these inputs, it automatically extracts matching furniture from the IKEA dataset using the CLIP model, based on:
   - Room type  
   - Room style  
   - Furniture type  

3. Automatically removes the background of furniture images using rembg.

4. Creates a layout that includes the window and door positions along with the selected furniture images.

5. Constructs a full prompt and sends it, along with the layout, to the Stable Diffusion model using ControlNet.

6. Evaluates the generated design using two fine-tuned VGG classifiers (one trained on room types and the other on room styles) to generate a matching score between the generated design and the user’s input (room type and style).

---

##  Datasets Used

This project uses three publicly available datasets:

- IKEA Furniture Dataset – For furniture classification  
   [Roboflow Link](https://universe.roboflow.com/projet-ai/ikea-furnitures/dataset/2)

- *House Rooms Image Dataset* – For room type classification  
   [Kaggle Link](https://www.kaggle.com/datasets/robinreni/house-rooms-image-dataset)

- Interior Design Styles Dataset – For room style classification  
   [Kaggle Link](https://www.kaggle.com/datasets/stepanyarullin/interior-design-styles)

> Note: We applied a custom filtering process to the IKEA dataset (e.g., removing full-room images) before using it in the model.

---

##  Data License Notice

Important: The "Interior Design Styles" dataset contains images scraped from Houzz.com, which are copyrighted.  
These images are provided strictly for academic and research purposes.  
Please do not redistribute or use the images in any commercial or public setting.  
Users must download the datasets directly from the original sources.

---

##  How to Run

1. Open the project in Google Colab 
    [Open in Colab]([YOUR_COLAB_LINK_HERE](https://colab.research.google.com/drive/17H8tYgIIZx9IsUZgw5ym1UaR1LQIZYgB?usp=sharing)

2. Download the original datasets from the links above and place them in the following folders:
   - IKEA Furniture Dataset → /content/unzipped_data/content/all_data_filtered  
   - Room Type Dataset → /content/rooms_data/House_Room_Dataset  
   - Room Style Dataset → /content/styles_data/dataset_train  

3. Run each cell step by step:
   - Provide user input (room type, style, dimensions, door/window positions, type of furniture)  
   - Furniture is selected using CLIP  
   - Layout is generated and sent to Stable Diffusion with the full prompt  
   - Output is evaluated using the VGG classifiers  

4. Final Output:
   - A realistic room design  
   - A matching score that reflects how well the generated design fits the user’s input (room type and style)

---

##  Research Paper

This paper was written as part of our final Advanced AI course project at Princess Nourah bint Abdulrahman University.  
Although it is not published in a journal, it follows the structure and rigor of an academic research paper.  
 You can read the full paper  [here]([DecoMind Research paper (1).pdf](https://github.com/user-attachments/files/21198694/DecoMind.Research.paper.1.pdf)
).
