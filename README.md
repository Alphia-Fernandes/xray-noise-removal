
# Restoration of Noisy Medical Images Using Median Filtering

## Team Members

| Name                    | USN         |
|-------------------------|-------------|
| Alphia Frenita Fernandes| 4SO22CD003  |
| Bhoomika Rai            | 4SO22CD012  |
| Tanvi Shetty            | 4SO22CD057  |

---

## 1. Introduction

Digital Image Processing (DIP) is now an essential tool for solving real-world problems across many fields, especially medical imaging. With improved hardware and algorithms, we are now able to process, restore, and extract useful information from images that were otherwise unusable because of noise, distortion, or low resolution. Of all the techniques in DIP, image restoration plays a very important role when handling corrupted or degraded images.

Medical images are generally plagued by various forms of noise, including salt-and-pepper noise, Gaussian noise, or speckle noise, at the time of image acquisition, transmission, or compression. Restoration of such noisy images is important since proper diagnosis and treatment depend significantly on the quality and sharpness of such images. Through this project, we illustrate the use of median filtering to restore noisy grayscale medical images plagued by salt-and-pepper noise. This is a typical noise form in digital medical image files like X-rays, MRI scans, and ultrasound images.

We want to achieve this with a basic, interpretable, and working implementation using Python with OpenCV and Matplotlib libraries. The result is a denoised image that maintains edges and key structures while erasing noise artifacts. This work is intended to not only display the capability of simple DIP methods but also lay a ground for future applications involving more complex denoising and segmentation. Finally, the paper highlights the real-world applications of theoretical principles learned in Digital Image Processing and stresses the need for effective image restoration algorithms in medical diagnosis and computer vision applications.


---

## 2. Problem Statement

**"To develop an image restoration application capable of removing salt-and-pepper noise from grayscale medical images using the median filtering technique."**

### Objective

For employing Digital Image Processing (DIP) techniques in noisy medical image restoration and in visually comparing the effectiveness of the median filter to remove noise as well as in retaining critical structures from medical scans.

### Scope
This project focuses on:
- Apply median filtering to grayscale images.
- Visualize comparison between noisy and restored images.
- Provide a base for future image restoration and segmentation tools.
The extent of this work is kept low deliberately to concentrate on illustrating the capability of a single, but highly powerful, image restoration algorithm. The concepts shown here are very easily extensible. The general denoising framework can be integrated with advanced pre-processing algorithms, classification structures, and diagnostic modules for field deployment. 
---

## 3. Dataset and Image Sources

In this project, we simulate noisy medical images by artificially adding salt-and-pepper noise to publicly available grayscale medical images (such as chest X-rays or MRI slices). These can be obtained from:

- [NIH Chest X-ray Dataset](https://www.kaggle.com/nih-chest-xrays/data)
- [RSNA Pneumonia Detection Challenge](https://www.kaggle.com/c/rsna-pneumonia-detection-challenge)
- [OASIS Brain Imaging Dataset](https://www.oasis-brains.org/)

Image used: `1.png` (located in `noisy_images/`)

---

## 4. Tools and Technologies Used

To ensure efficient development and experimentation, we used the following tools:
•	Programming Language: Python 3.9+  
•	Libraries:  
o	OpenCV (cv2) for image processing functions.  
o	Matplotlib for visualization of images.  
o	OS module for file handling.  

**Software Requirements:**  
•	Anaconda/Miniconda with Jupyter Notebook support  
•	Python environment with installed dependencies  

**Installation:**  
To install the required libraries, use the following command:  
“pip install opencv-python matplotlib”

**Why Python and OpenCV?**  
Python has extensive use in image processing and machine learning owing to its simple syntax and rich ecosystem of libraries. OpenCV, which is an acronym for Open-Source Computer Vision Library, offers many functions to handle and analyze images, making it ideal for this application.


---

## 5. Code Explanation and Workflow

The core of our project is a Python script that performs the following steps:

### a) Directory Setup

Two folders are required:

- `noisy_images/`: Contains the original noisy image(s).
- `denoised_output/`: Stores the denoised output(s).

This organizational structure helps separate inputs from outputs and ensures ease of use for future development.

```python
noisy_folder = "noisy_images"
denoised_folder = "denoised_output"
os.makedirs(denoised_folder, exist_ok=True)
```

## 6. Technique Used: Median Filtering

### What is Median Filtering?

Median filtering is a **non-linear digital filtering** method for eliminating noise from an image. It works best for **salt-and-pepper noise**, which appears as randomly distributed white and black pixels.

### How it Works:

- A kernel (typically 3x3) traverses the image.
- For each pixel, the kernel considers its surrounding neighborhood.
- The central pixel is replaced with the **median** of the neighboring pixel values.

This technique **preserves edges** and performs better than linear filters like mean filters when dealing with impulse noise.

### Why Median Filter?

- Preserves edges more effectively than linear filters (e.g., Gaussian).
- Eliminates extreme values (salt or pepper pixels) effectively.
- Simple and fast.
- Easy to implement.
- Reduces image distortion compared to averaging filters.

Median filtering is most effective when noise is not Gaussian and appears as **high-intensity spikes (pepper)** or **low-intensity dips (salt)**.

---

## 7. Real-World Application Relevance

### a) Medical Imaging

- Enhancing X-ray, MRI, and CT scan images for better visibility.
- Pre-processing step before segmentation or detection.
- Used in diagnostic systems for bone fracture detection, tumor analysis, and organ boundary identification.

### b) Satellite Imaging

- Restoration of images distorted due to atmospheric noise.
- Useful in remote sensing and land use mapping.

### c) Document Image Processing

- Cleaning scanned documents before OCR (Optical Character Recognition).
- Improving readability of low-quality scanned images.

This project, though simple, replicates a crucial step in these applications by improving image clarity and preparing data for downstream tasks such as classification, segmentation, or enhancement.

---

## 8. Program Flow Diagram

```
Start → Load Noisy Image → Apply Median Filter → Save Denoised Image → Display Comparison → End
```

---

## 9. Future Scope and Enhancements

While the current implementation is simple and limited to median filtering, the project can be enhanced in multiple ways:

### a) Integration with Advanced Filters

- **Bilateral Filtering**: Combines range and domain filtering.
- **Non-Local Means Denoising**: Considers similar patches across the image.
- **Wavelet Denoising**: Denoising in frequency space.

### b) Multi-channel (Color) Image Support

- Extend to handle RGB or color medical images.
- More complex as each channel must be processed correctly.

### c) GUI-based Application

- Develop a simple GUI for uploading noisy images and viewing denoised results.
- Use frameworks like **Tkinter**, **PyQt**, or **Streamlit**.

### d) Segmentation Integration

- Apply thresholding and segmentation to highlight regions of interest (tumors, bones).
- Integrate with OpenCV **contour detection** or **watershed segmentation**.

### e) AI-Enhanced Restoration

- Use Deep Learning (**Denoising Autoencoders**, **GANs**) for smarter noise removal.
- Train on large datasets to generalize across modalities.
- Integrate **TensorFlow** or **PyTorch** for scalable models.

### f) Performance Evaluation

- Use metrics like **PSNR** (Peak Signal-to-Noise Ratio) and **SSIM** (Structural Similarity Index) to quantitatively evaluate performance.
- Benchmark against ground truth images.

---

## 10. References

- Gonzalez & Woods, *Digital Image Processing*, 4th Ed.
- [OpenCV Docs](https://docs.opencv.org/)
- [NIH Chest X-ray Dataset](https://www.kaggle.com/nih-chest-xrays/data)
- [RSNA Pneumonia Dataset](https://www.kaggle.com/c/rsna-pneumonia-detection-challenge)
- [OASIS Dataset](https://www.oasis-brains.org/)
- Anil K. Jain, *Fundamentals of Digital Image Processing*
- *Digital Image Processing Using MATLAB*
- S. Mallat, *A Wavelet Tour of Signal Processing*

---

## 11. Conclusion

This project shows a hands-on method of addressing the actual issue of image degradation in medical imaging through simple digital image processing methods. We applied and experimented with a median filtering algorithm to repair grayscale medical images that have been contaminated with salt-and-pepper noise. The outputs confirm how ancient filtering processes, although simple, are quite useful in enhancing image quality and usability.
The project sets the stage for incorporating more advanced image processing methods like segmentation, morphological operations, and even AI-based denoising techniques. It demonstrates how fundamental techniques learned in class are extremely useful and applicable in actual medical diagnostic systems.
Our long-term vision is to advance this framework to a full-fledged image preprocessing and analysis pipeline, eventually facilitating automated diagnostics in clinical environments. The learning achievements of this project are an in-depth understanding of noise removal, Python implementation using OpenCV, and knowledge about real-world applications of digital image processing. We also understand the significance of modular and scalable design in creating real-world image processing pipelines.
With additional improvements, this project can be expanded into an effective tool by integrating classical and contemporary image processing for real-time diagnostic support.


---
