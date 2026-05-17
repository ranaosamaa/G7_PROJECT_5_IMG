
# Image Processing with Matrices (C++)

A C++ console-based image processing project that demonstrates fundamental image manipulation techniques using matrix operations. The project operates on **PPM (P3) images** and implements several common transformations without relying on external libraries.

---

## Features

* **Custom Image Class**

  * Stores image data as a 3D matrix `[height][width][channels]`
  * Supports RGB and grayscale images

* **Supported Image Operations**

  * Grayscale conversion
  * Horizontal flip
  * Vertical flip
  * Brightness adjustment
  * Contrast adjustment
  * Blur filter (3×3 averaging kernel)
  * 90° rotation (clockwise)

* **File Handling**

  * Load images in PPM (P3) format
  * Save processed images as PPM files

* **Test Image Generator**

  * Automatically creates a 4×4 sample image for testing
  * Prints pixel data to console for verification

---

## Project Structure

```bash
.
├── main.cpp
├── Image class              # Image representation and I/O
├── Processing functions     # Transformations (grayscale, blur, etc.)
└── Output images (.ppm)     # Generated after execution
```

---

## How It Works

1. A test image (`test_image.ppm`) is generated.
2. The image is loaded into memory.
3. Multiple transformations are applied sequentially.
4. Each result is saved as a new `.ppm` file.
5. Pixel values are printed to the console for inspection.

---

## How to Compile and Run

### Compile

```bash
g++ -o image_processor main.cpp
```

### Run

```bash
./image_processor
```

---

## Output Files

After execution, the following images are generated:

* `test_image.ppm` — Original test image
* `gray_image.ppm` — Grayscale version
* `flipped_horizontal.ppm` — Horizontally flipped
* `flipped_vertical.ppm` — Vertically flipped
* `bright_image.ppm` — Brightness adjusted
* `contrast_image.ppm` — Contrast adjusted
* `blurred_image.ppm` — Blurred image
* `rotated90_image.ppm` — Rotated image

---

## Image Processing Details

### Grayscale Conversion

Uses weighted average:

```
gray = 0.299 * R + 0.587 * G + 0.114 * B
```

### Brightness Adjustment

```
new_value = clamp(pixel + value, 0, 255)
```

### Contrast Adjustment

```
new_value = clamp(factor * (pixel - 128) + 128, 0, 255)
```

### Blur Filter

* Applies a **3×3 averaging kernel**
* Each pixel becomes the average of its neighbors

### Rotation

* Rotates image **90° clockwise**
* Swaps width and height

---

## Requirements

* C++ compiler (GCC, Clang, or MSVC)
* No external libraries required

---

## Limitations

* Only supports **PPM (P3) format**
* No GUI (console-based output)
* Blur does not process border pixels with kernel (keeps original values)

---

## Future Improvements

* Add support for other formats (PNG, JPG)
* Implement edge detection (Sobel, Canny)
* Add histogram equalization
* Optimize performance (avoid redundant copying)
* Add GUI visualization

---

## Concepts Demonstrated

* 3D vector data structures
* Image representation in memory
* Pixel-wise transformations
* Convolution (blur filter)
* File I/O handling
* Modular function design

---

## Author

Developed as a foundational image processing and matrix manipulation project in C++.

---
