# 8-Bit XOR Encryption and Decryption in Python

## Project Overview

This project implements an 8-bit XOR Cipher (Key = `11000011`) in Python. The Python implementation is used as a reference for the corresponding SystemVerilog implementation.

The implementation demonstrates XOR encryption and decryption for:

1. A single 8-bit number
2. A 16-byte vector
3. A 256 × 256 8-bit grayscale image

The same XOR operation is used for both encryption and decryption.

## Repository Structure

```text
XOR-encryption-and-decryption-in-Python/
│
├── README.md
├── xor_encryption_python.ipynb
│
├── data/
│   └── input_image.jpeg
│
└── outputs/
    ├── original_python.png
    ├── encrypted_python.png
    ├── decrypted_python.png
    ├── image_comparison.png
    └── image_test_vectors.csv
```

## How to Run

### Google Colab

1. Open `xor_encryption_python.ipynb`.
2. Open the notebook in Google Colab.
3. Run the code.
4. When prompted, upload a 256 × 256 image.
5. The notebook converts the image to 8-bit grayscale.
6. The image is encrypted using the fixed XOR key `0xC3`.
7. The encrypted image is decrypted using the same key.
8. Verification results are displayed.
9. The generated images and CSV test-vector file are saved in the `xor_results` directory.

## Output Files

The `outputs/` directory contains:

- `original_python.png`
- `encrypted_python.png`
- `decrypted_python.png`
- `image_comparison.png`
- `image_test_vectors.csv`

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
| 256 × 256 grayscale image | PASS |

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
