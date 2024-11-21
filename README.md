

# Reversible Data Hiding in Images

This repository implements a **Reversible Data Hiding** (RDH) technique that embeds binary data into grayscale images. The method ensures that both the embedded data and the original image can be perfectly restored after extraction. It uses pixel difference analysis, histogram shifting, and optimized transformations for high capacity and low distortion.



## Features
- **Embed and Extract Data**: Embed binary data into images and recover both the data and the original image without loss.
- **High Embedding Capacity**: Achieve a significant amount of data embedding while maintaining visual quality.
- **Visual Quality Evaluation**: Calculate Peak Signal-to-Noise Ratio (PSNR) to evaluate embedding effects.
- **Histogram Analysis**: Analyze the embedding impact using Pixel Difference Histogram (PDH).
- **Flexible Transformations**: Support for both column-wise and row-wise transformations.

---

## Prerequisites

To run this project, ensure you have Python 3.8 or later and the following libraries installed:
- **NumPy**
- **Pillow**
- **Matplotlib**

Install the dependencies using:
```bash
pip install numpy pillow matplotlib
```

---

## How to Use

### Clone the Repository
```bash
git clone https://github.com/yourusername/reversible-data-hiding.git
cd reversible-data-hiding
```

### Run the Script
1. Add your image to the repository directory.
2. Open the script and set the `path` variable to your image's path.
3. Modify the `data` variable to the binary string you want to embed.

#### Example
```python
if __name__ == "__main__":
    path = "your_image.jpg"  # Path to your grayscale image
    data = "1010101010"      # Binary data to embed
    marked_img, recovered_img = process(path, data, axis="columns")
```

### Outputs
- **Images**:
  - Original Image
  - Marked Image (with embedded data)
  - Recovered Image (restored after data extraction)
- **Extracted Data**:
  - Displays the binary data extracted from the marked image.
- **Quality Metrics**:
  - Prints the Peak Signal-to-Noise Ratio (PSNR).
- **PDH Visualization**:
  - Shows the impact of embedding on pixel differences.

---

## Code Explanation

### Main Functions
1. **`embed_data`**:
   - Embeds binary data into the image using histogram shifting.
   - Handles overflow and underflow with a location map.

2. **`extract_data`**:
   - Extracts embedded data and reconstructs the original image.

3. **`psnr`**:
   - Calculates PSNR to measure visual similarity.

4. **`pdh_analysis`**:
   - Visualizes pixel difference distributions before and after embedding.

5. **`process`**:
   - Orchestrates the workflow: embedding, extraction, and visualization.

### Visualization
The script displays side-by-side comparisons of:
1. Original Image
2. Marked Image
3. Recovered Image

---

## Sample Code
Here’s how to embed and extract data:
```python
# Example Usage
if __name__ == "__main__":
    path = "example_image.jpg"  # Input grayscale image
    data = "1010101010"         # Binary data to embed
    
    # Embed and extract
    marked_img, recovered_img = process(path, data, axis="columns")

    # Save results
    Image.fromarray(marked_img.astype(np.uint8)).save("marked_image.png")
    Image.fromarray(recovered_img.astype(np.uint8)).save("recovered_image.png")
```

---

## Results

- **Embedding Capacity**: High, optimized using column-wise/row-wise transformations.
- **PSNR**: Measures visual quality after embedding (e.g., >35 dB).
- **Reversibility**: Both data and original image are perfectly recoverable.

---

## References

This project is based on the research paper:  
[Reversible Data Hiding Techniques with High Message Embedding Capacity in Images](https://arxiv.org/abs/2203.01178)

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contributing

Contributions are welcome!  
Feel free to fork the repository, create a new branch, and submit a pull request. For major changes, please open an issue first to discuss what you would like to modify.

---

## Contact
If you have any questions or issues, feel free to reach out:  
**Ananya Tomar** -ananyatomar2308@gmail.com
```

