# Image Steganography with Python

This Python script demonstrates a simple implementation of steganography, a technique of hiding secret data within an ordinary, non-secret file or message to avoid detection. In this case, the script hides a binary stream representing a sentence within an image file.

## How it Works

### Step 1: Convert the Sentence to a Binary Stream

The `sentence_to_binary` function takes a sentence as input and converts it into a binary stream. Each character in the sentence is converted to its 7-bit ASCII representation and then to binary. Characters outside the ASCII range are skipped.

### Step 2: Choose an Image and Modify its Pixels

The `hide_binary_in_image` function takes an image file path and the binary stream as input. It modifies the least significant bit of each color channel (RGB) of the image pixels to encode the binary stream. This process is done iteratively until all bits of the binary stream are encoded or until there are no more pixels available in the image.

### Step 3: Saving the Encoded Image

The modified image with the hidden message is saved as `encoded_image.png` in the `_files` directory.

### Step 4: Create a Word File Containing Sentence Details

The `save_to_word_file` function saves details about the sentence, including the sentence itself, its integer ASCII codes, binary ASCII codes, and the binary stream, into a Word file named `sentence_details.docx` in the `_files` directory.

## Usage

1. Ensure you have Python installed on your system.
2. Install the required dependencies using `pip install pillow`.
3. Place the image you want to encode the message into in the `_files` directory and update the `image_path` variable in the script accordingly.
4. Run the script. The encoded image (`encoded_image.png`) and the Word file (`sentence_details.docx`) will be generated in the `_files` directory.

## Note

- The script currently supports ASCII characters only. Non-ASCII characters will be skipped during encoding.
- Make sure the binary stream does not exceed the available capacity of the image to avoid data loss or corruption.

## Author

[*Mohamed Essam*](https://github.com/m-essam-s)
