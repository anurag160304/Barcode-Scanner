# Barcode Scanner with Authorization Check

This project implements a real-time barcode scanner using Python and OpenCV. It decodes barcodes from a webcam feed and verifies the data against a pre-defined list of authorized entries.

---

## Features

- **Real-Time Barcode Detection**: Uses OpenCV and Pyzbar to detect and decode barcodes.
- **Authorization Check**: Compares decoded data against a list of authorized entries stored in a text file (`mydataFile.text`).
- **Visual Feedback**: Displays the scanning result in real-time with a bounding polygon and color-coded text indicating authorization status.

---

## Prerequisites

Ensure you have the following installed:

- Python 3.x
- OpenCV
- NumPy
- Pyzbar

Install the required libraries using pip:

```bash
pip install opencv-python-headless numpy pyzbar
```

---

## Project Structure

- `barcode_scanner.py`: Main Python script for barcode scanning and authorization.
- `mydataFile.text`: Text file containing authorized barcode data (one entry per line).

---

## How It Works

1. **Webcam Setup**: Initializes the webcam with specific resolution settings.
2. **Barcode Decoding**: Decodes barcodes in the webcam feed using Pyzbar.
3. **Authorization Check**: Verifies decoded barcode data against entries in `mydataFile.text`.
4. **Visual Feedback**: Displays real-time feedback with bounding polygons and text (green for authorized, red for unauthorized).

---

## Usage

1. Create a text file named `mydataFile.text` and populate it with authorized barcode data, one entry per line:

   ```
   1234567890
   ABCD1234
   QRDATA5678
   ```

2. Run the script:

   ```bash
   python barcode_scanner.py
   ```

3. Point the webcam at a barcode. The script will:
   - Display a bounding polygon around the detected barcode.
   - Show `Authorized` (green) or `Un-Authorized` (red) based on the barcode data.

4. Press `Ctrl + C` or close the webcam window to terminate the script.

---

## Customization

- **Adjust Resolution**:
  Modify the following lines to set the desired webcam resolution:

  ```python
  cap.set(3, 640)  # Width
  cap.set(4, 480)  # Height
  ```

- **Change File Path**:
  Update the path to `mydataFile.text` if it is stored in a different location.

- **Enhanced Feedback**:
  Modify colors and text styles in the following lines:

  ```python
  myColor = (0, 255, 0)  # Green for authorized
  myColor = (0, 0, 255)  # Red for unauthorized
  ```

---

## Limitations

- Requires a well-lit environment for optimal barcode detection.
- Limited to barcodes supported by the Pyzbar library.

---

## License

This project is open-source and available under the MIT License.
