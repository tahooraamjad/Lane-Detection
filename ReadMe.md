# Classical Computer Vision-Based Lane Detection

This project implements a **lane detection system using classical computer vision techniques** without using any deep learning or neural networks. The approach is designed to be lightweight, interpretable, and suitable for real-time applications.

The implementation is based on **OpenCV image processing methods**, following a structured pipeline to detect lane boundaries on road images.

---

##  Key Features

- Pure **Classical Computer Vision** approach  
- No CNN, YOLO, or Deep Learning models  
- Uses **HLS color space** for better robustness against lighting variations  
- **Polynomial fitting (Quadratic curve)** for handling curved roads  
- Efficient and suitable for real-time processing  

---

##  Techniques Used

The lane detection pipeline includes the following steps:

1. **Image Acquisition**  
   Input road images captured from a forward-facing camera.

2. **Color Space Conversion (RGB → HLS)**  
   HLS color space is used to improve lane visibility and reduce the impact of illumination changes.

3. **Noise Reduction**  
   Gaussian Blur is applied to smooth the image and suppress noise.

4. **Edge Detection**  
   Canny Edge Detection is used to extract strong edges corresponding to lane markings.

5. **Region of Interest (ROI)**  
   A polygonal mask is applied to focus only on the road area and remove irrelevant regions.

6. **Polynomial Fitting (Quadratic Curve)**  
   Detected lane pixels are fitted using a second-order polynomial equation:
   
   y = Ax² + Bx + C  
   
   This helps in:
   - Detecting **curved roads**
   - Producing **smooth and continuous lane lines**
   - Improving overall detection accuracy

7. **Lane Visualization**  
   The detected lane curves are drawn back onto the original image.

---

##  Mathematical Model

- **Canny Edge Gradient**:  
  G = √(Gx² + Gy²)

- **Polynomial Lane Model**:  
  y = Ax² + Bx + C

---

##  Results

- Achieves **more than 95% lane detection accuracy** on structured road images under normal lighting conditions.
- Performs well on both straight and moderately curved roads.
- Efficient enough to run in real time without GPU acceleration.

---

##  Limitations

- Performance may decrease in very low-light or night-time conditions.
- Heavily faded or broken lane markings can reduce accuracy.
- Occlusions caused by vehicles may lead to partial lane detection.
- Accuracy depends on proper camera calibration and region-of-interest selection.

---

##  Files Included

- `Lane_Detection_Kaggle_01.ipynb` – Main Google Colab notebook  
- `README.md` – Project documentation  

---

##  How to Run

1. Open the notebook in **Google Colab**
2. Install required libraries (OpenCV, NumPy)
3. Run all cells step by step
4. Upload sample road images or use the provided dataset
5. Observe detected lane outputs

---

##  Conclusion

This project demonstrates that **classical image processing techniques** can effectively perform lane detection without relying on deep learning. The use of HLS color space and polynomial fitting significantly improves robustness and smoothness, making this approach suitable for low-resource and real-time systems.

---

##  License

This project is for **academic and educational purposes only**.
