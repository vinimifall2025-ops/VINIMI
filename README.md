# VINIMI

This project focuses on **ensuring workplace safety compliance** by detecting personnel, identifying individuals, and verifying whether they are wearing appropriate **Personal Protective Equipment (PPE)** such as helmets. The pipeline integrates **face recognition**, **helmet detection**, and a **vision-language interface** for querying images.

---

## What We Have Done

1. **Synthetic Dataset Creation**  
   - Generated **450 photo-realistic images** using **Stable Diffusion (Realistic Vision V5.1)**.  
     - 225 images with helmets, 225 without helmets.  
   - Each person assigned **unique metadata**: name, gender, age, appearance traits.  
   - **50+ diverse construction & industrial scenes** included.  
   - Images organized into `helmet/` and `no_helmet/` directories.  
   - [Wiki Page: Synthetic Dataset](https://github.com/vinimifall2025-ops/VINIMI/wiki/Synthetic-Dataset)

2. **Metadata Preparation**  
   - Created `person_metadata.csv` linking each image to identity and a unique mobile number.  
   - Supports downstream face recognition and person-specific analysis.  
   - [Wiki Page: Metadata Preparation](https://github.com/vinimifall2025-ops/VINIMI/wiki/Metadata-Preparation)

3. **Face Recognition**  
   - Used **DeepFace** with **VGG-Face** to extract **4096-dimensional embeddings** for each face.  
   - Performed recognition using **cosine similarity** between embeddings.  
   - Visualized detected faces with bounding boxes using **OpenCV** and **matplotlib**.  
   - Provided downloadable resources:
     - [person_metadata.csv](https://github.com/vinimifall2025-ops/VINIMI/blob/main/people_metadata.csv)  
     - [face_embeddings.csv](https://github.com/vinimifall2025-ops/VINIMI/blob/main/face_embeddings.csv)  
   - [Wiki Page: Face Recognition](https://github.com/vinimifall2025-ops/VINIMI/wiki/Face-Recognition)

4. **Helmet Detection**  
   - Used **YOLOv8** with pretrained weights (`best.pt`) to detect helmets and related PPE.  
   - Download weights with:
     ```bash
     !wget https://huggingface.co/keremberke/yolov8m-hard-hat-detection/resolve/main/best.pt -O best.pt
     ```
   - Generated predictions with **annotated bounding boxes** and visualized results.  
   - [Wiki Page: Helmet Detection](https://github.com/vinimifall2025-ops/VINIMI/wiki/Helmet-Detection)

---

## Next Steps

- Integrate **alerting system** to notify individuals via SMS or WhatsApp if safety violations are detected.  
- Extend **Vision-Language Q&A** to allow intuitive queries like “Is this person wearing a helmet?” or “Who is this?”  

---

## References & Wiki

For **detailed explanations, example images, and code snippets**, please refer to the project wiki:  

[VINIMI Project Wiki](https://github.com/vinimifall2025-ops/VINIMI/wiki)
