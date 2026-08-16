# 8-Bit XOR Encryption and Decryption in Python

## Project Overview

This repository contains the Python reference implementation for an 8-bit XOR encryption and decryption exercise.

The implementation demonstrates XOR encryption and decryption for:

1. A single 8-bit number
2. A 16-byte vector
3. A 256 Ã— 256 8-bit grayscale image

The same XOR operation is used for both encryption and decryption.

## Repository Structure

```text
XOR-encryption-and-decryption-in-Python/
â”‚
â”œâ”€â”€ README.md
â”œâ”€â”€ xor_encryption_python.ipynb
â”‚
â”œâ”€â”€ data/
â”‚   â””â”€â”€ input_image.jpeg
â”‚
â””â”€â”€ outputs/
    â”œâ”€â”€ original_python.png
    â”œâ”€â”€ encrypted_python.png
    â”œâ”€â”€ decrypted_python.png
    â”œâ”€â”€ image_comparison.png
    â””â”€â”€ image_test_vectors.csv
```

## How to Run

### Google Colab

1. Open `xor_encryption_python.ipynb`.
2. Open the notebook in Google Colab.
3. Run the code.
4. When prompted, upload a 256 Ã— 256 image.
5. The notebook converts the image to 8-bit grayscale.
6. The image is encrypted using the fixed XOR key `0xC3`.
7. The encrypted image is decrypted using the same key.
8. Verification results are displayed.
9. The generated images and CSV test-vector file are saved in the `xor_results` directory.

## Output Files

The `outputs` directory contains:

- `original_python.png` â€” original grayscale image
- `encrypted_python.png` â€” XOR-encrypted image
- `decrypted_python.png` â€” decrypted image
- `image_comparison.png` â€” visual comparison
- `image_test_vectors.csv` â€” pixel-level test vectors

## XOR Key

The fixed 8-bit key used in this implementation is:

- Binary: `11000011`
- Hexadecimal: `0xC3`
- Decimal: `195`

Encryption:

`Ciphertext = Plaintext XOR Key`

Decryption:

`Plaintext = Ciphertext XOR Key`

## Part 1: Single 8-Bit Number

The test plaintext is `200`.

Using the key `195`:

`200 XOR 195 = 11`

Decrypting with the same key:

`11 XOR 195 = 200`

The original plaintext is successfully recovered.

## Part 2: 16-Byte Vector

The 16-byte vector used is:

```text
[10, 200, 55, 128, 0, 255, 77, 33,
 9, 250, 61, 190, 5, 222, 100, 47]
```

The resulting ciphertext is:

```text
[201, 11, 244, 67, 195, 60, 142, 226,
 202, 57, 254, 125, 198, 29, 167, 236]
```

The ciphertext is XORed with the same key to recover the original vector.

## Part 3: 256 Ã— 256 Grayscale Image

The image implementation uses a 256 Ã— 256 grayscale image.

Requirements:

- Width: 256 pixels
- Height: 256 pixels
- Channels: 1
- Pixel type: 8-bit unsigned integer
- Total pixels: 65,536

Each pixel is encrypted using:

`Encrypted Pixel = Original Pixel XOR 0xC3`

The encrypted image is then decrypted using the same key.

## Verification

The implementation performs the following checks:

### Pixel-by-Pixel Verification

The decrypted image is compared with the original image.

- Different pixels: `0`
- Maximum pixel difference: `0`

### Ciphertext Verification

The encrypted image is independently calculated using NumPy XOR and compared with the encryption output.

### SHA-256 Verification

The SHA-256 hash of the original image data is compared with the hash of the decrypted image data.

### Test Vectors

A CSV file containing all 65,536 image pixels is generated.

Each row contains:

- Pixel index
- Row
- Column
- Plaintext value
- Ciphertext value
- Decrypted value

## Results

| Test | Result |
|---|---|
| Single 8-bit number | PASS |
| 16-byte vector | PASS |
| 256 Ã— 256 grayscale image | PASS |

Image verification:

| Verification | Result |
|---|---|
| Total pixels | 65,536 |
| Different pixels | 0 |
| Maximum difference | 0 |
| Ciphertext check | PASS |
| Decryption check | PASS |
| SHA-256 check | PASS |

## Relationship to the SystemVerilog Implementation

This Python implementation serves as a software reference for the 8-bit XOR encryption and decryption operation.

The fixed key and 16-byte reference vector are kept consistent with the SystemVerilog work so that the software and hardware implementations can be compared.



