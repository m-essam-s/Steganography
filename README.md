# Steganography Project

This project implements a steganography technique to hide a sentence in both an image and a text file. The required sentence is based on the student's first name and student ID, which is then converted into a binary stream and embedded within the chosen files.

## Project Structure

```
.
├── img_24_bit_depth_steganography
│   ├── Cameraman_graycale.jpg
│   ├── encoded_image.png
├── text_file_steganography
│   ├── Original_text.txt
│   ├── text_after_steganography.txt
├── sentence_details
│   ├── details.txt
│   ├── details.docx
├── steganography.py
├── README.md
```

## How It Works

1. **Sentence Conversion to Binary Stream**: The sentence, constructed from the student's first name and ID, is converted into a 7-bit binary stream.
2. **Embedding in Image**: The binary stream is embedded into the least significant bits of the RGB values of the image.
3. **Embedding in Text**: The binary stream is embedded into a text file by replacing single spaces with double spaces where needed.
4. **Saving Details**: The details of the sentence, including its binary and integer ASCII representations, are saved into both a text file and a Word document.

## Detailed Steps

### Step 1: Convert Sentence to Binary Stream

The function `sentence_to_binary(sentence)` converts each character in the sentence to its 7-bit ASCII representation and concatenates these binary values to form a single binary stream.

### Step 2: Embed Binary Stream in Image

The function `embed_bits_in_image(image_path, binary_stream)` performs the following:

- Opens the image and converts it to RGB mode if necessary.
- Checks if the binary stream can fit within the image pixels.
- Iterates through the image pixels, embedding each bit of the binary stream into the least significant bit of the RGB channels.
- Saves the modified image.

### Step 3: Embed Binary Stream in Text

The function `embed_bits_in_text(text_file_path, binary_stream)` performs the following:

- Reads the original text file.
- Iterates through the text, replacing single spaces with double spaces based on the binary stream.
- Writes the modified text to a new file.

### Step 4: Save Sentence Details

The function `save_to_file(sentence, binary_stream)` performs the following:

- Writes the sentence details to a text file.
- Creates a Word document containing a table with the sentence details.

## Prerequisites

- Python 3.x
- PIL (Pillow)
- python-docx

You can install the required libraries using pip:

```
pip install Pillow python-docx
```

## Usage

1. Ensure your files are in the correct directories:
   - Place your image file in `./img_24_bit_depth_steganography/` and update `image_path` in the script.
   - Place your original text file in `./text_file_steganography/` and update `text_file_path` in the script.

2. Update the `first_name` and `student_id` variables in the `main()` function with your details.

3. Run the script:

```
python steganography.py
```

4. Check the generated files:
   - Encoded image: `./img_24_bit_depth_steganography/encoded_image.png`
   - Text after steganography: `./text_file_steganography/text_after_steganography.txt`
   - Sentence details:
     - Text file: `./sentence_details/details.txt`
     - Word document: `./sentence_details/details.docx`

## Example

For a student named "Mohamed" with ID "221101060":

- The sentence is `Mohamed_221101060$`
- The 7-bit ASCII binary stream is generated and embedded into both an image and a text file.

## Notes

- Ensure the image is large enough to accommodate the binary stream.
- The text file should have sufficient spaces to encode the binary stream without altering the content drastically.

## Author

[*Mohamed Essam*](https://github.com/m-essam-s)
