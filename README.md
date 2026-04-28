# 🔐 Face Security System

An intelligent, multi-person facial recognition access system built using deep learning and computer vision. This system uses transfer learning to classify faces in real-time and grants or denies access based on a pre-defined list of authorized personnel.

## 📸 System in Action

*(Below are live demonstrations of the system successfully identifying authorized users and granting access via the Gradio interface).*

### Authorized Access: Prajwal
<img width="1920" height="1020" alt="Output-2" src="https://github.com/user-attachments/assets/9447300a-69aa-475b-beae-e35f78a5ef58" />


### Authorized Access: Dhanraj
<img width="1920" height="1020" alt="Output-1" src="https://github.com/user-attachments/assets/e4fb511d-2993-4aad-bb8a-4265dc38dcdc" />


---

## 🚀 Project Overview

This project is divided into a three-step pipeline:
1. **Face Extraction:** Uses MTCNN (Multi-task Cascaded Convolutional Networks) to scan bulk directories of full-length photos, detect faces, crop them, and save them into a cleaned dataset.
2. **Model Training:** Utilizes MobileNetV2 (pre-trained on ImageNet) via transfer learning to train a custom image classifier on the cropped faces. It employs data augmentation and early stopping to prevent overfitting.
3. **Deployment:** A web-based GUI built with Gradio that accepts webcam feeds or image uploads, scans the face, and returns an Access Granted/Denied status alongside confidence metrics and AI diagnostics.

## 🛠️ Tech Stack

* **Deep Learning Framework:** TensorFlow / Keras (MobileNetV2)
* **Computer Vision:** OpenCV, MTCNN
* **Interface / Deployment:** Gradio
* **Language:** Python

## 📂 Logic & Flow

* **Authorized Users:** The system is explicitly coded to grant access to authorized individuals (`Prajwal`, `Dhanraj`) provided the AI confidence score is >= 85.0%.
* **Access Denied:** Unrecognized faces or unauthorized individuals (e.g., testing with images outside the authorized list) will trigger an immediate "ACCESS DENIED" response.
* **Inconclusive Scans:** If an authorized user is detected but the confidence score falls below the 85.0% threshold, the system flags the scan as inconclusive for security purposes.
