# Steganography in Java

This project is a Java-based steganography tool that allows you to securely **encode** and **decode** secret files within PNG images using password protection. It utilizes Least Significant Bit (LSB) manipulation to embed data in an image without visibly altering it.

---

## How It Works

This tool uses **Least Significant Bit (LSB)** steganography, where the least significant bits of each color channel (Red, Green, Blue) in the image's pixels are modified to store binary data from the secret file.

### Encryption Process

1. A custom header is generated containing:
   - A magic number
   - The name of the secret file
   - A hash of the password
   - The length of the secret file

2. Both the header and the file content are converted to binary bits.

3. The bits are embedded into the LSBs of the image pixels.

4. A new output image is created that visually looks the same but carries the embedded secret.

During decryption, the tool validates the password using the hash and extracts the original secret file if the credentials are correct.

---

## Project Structure

```
/src
 ├── Program.java
 ├── Steganographer.java
 ├── HeaderManager.java
 └── Utility.java
```

---

## Compilation

### Step 1: Navigate to the `src` Folder

Open your terminal or command prompt and navigate to the `src` directory where all `.java` files are located.

```bash
cd src
```

### Step 2: Compile All Java Files

Run the following command to compile all the source files:

```bash
javac *.java
```

This will generate `.class` files for each source file.

---

## Running the Program

Once compiled, run the main class `Program`:

```bash
java Program
```

You will see the following menu:

```
1. Encode
2. Decode
3. Exit
```

---

## Encode Option

You will be prompted to enter:

- **Vessel file name** (e.g., `vessel.png`)
- **Secret file name** (e.g., `secret.txt`)
- **Password**

A new image (e.g., `output.png`) containing the hidden data will be created in the same directory.

---

## Decode Option

You will be prompted to enter:

- **File name** of the image containing the hidden data (e.g., `output.png`)
- **Password**

If the password matches the embedded hash, the secret file will be extracted and saved in the same directory.

---

## File Placement

Before running the program, ensure that:

- The compiled `.class` files are present in the current directory.
- The **vessel image** and **secret file** are in the same directory as `Program.class`.

---

## Requirements

- Java Development Kit (JDK) 8 or above
- Input image must be in `.png` format
- Terminal/Command Prompt access to compile and run Java programs

---

## Notes

- Only `.png` images are supported as vessel files.
- Use strong passwords for better protection.
- Ensure the vessel image is large enough to hold the secret file.

---