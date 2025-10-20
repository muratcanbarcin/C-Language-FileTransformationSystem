# C-Language File Transformation System

## Project Overview

This project is a command-line tool developed entirely in **C** for data organization and file format transformation. The primary function of this utility is to convert structured student data between **CSV**, **XML**, and a custom **Binary** format.

The project emphasizes low-level file I/O operations, data parsing, and format manipulation without relying on high-level libraries. A key component is the inclusion of an **XML Schema Definition (XSD)** file to ensure the structural and data type integrity of the generated XML output.

## Core Technical Features

* **Pure C Implementation:** All file parsing, data structuring, and generation logic are written from scratch in C.
* **Multi-Format Conversion:** The tool supports bidirectional conversion between multiple file types:
    * **CSV Parsing:** Reads and interprets the `records.csv` file.
    * **XML Generation:** Transforms the parsed data into a valid, structured XML file.
    * **Binary Generation:** Converts the records into a custom binary file format, managing the byte-level representation of data.
* **Binary Data Handling:** Implements logic for reading and writing binary files, including handling potential byte-order differences (**Little Endian vs. Big Endian conversion**).
* **XML Validation (XSD):** Includes a `records.xsd` file that defines a strict schema for the XML output. This schema enforces constraints on data types (e.g., `stuID` format), required fields, and value enumerations (e.g., `gender` must be 'M' or 'F').
* **Command-Line Interface (CLI):** The `converter` executable is operated via command-line arguments, which specify the input file, output file, and the desired operation (e.g., conversion type or validation).

## How to Use

1.  Compile the C source file using `gcc` or a similar C compiler:
    ```bash
    gcc converter.c -o converter
    ```

2.  Run the compiled executable from the command line. The program requires arguments to specify the mode of operation (e.g., CSV-to-XML, XML-to-Binary, Validate-XML).

3.  **Example Command (for XML Validation):**
    The following command would be used to validate an existing `records.xml` file against its schema `records.xsd`, using mode `3` (as specified in the project documentation).
    ```bash
    ./converter records.xml records.xsd 3
    ```

## Key Project Files

* **`converter.c`**: The main C source code containing all logic for parsing and file operations.
* **`records.csv`**: The sample input data file containing student records.
* **`records.xsd`**: The XML Schema Definition used to validate the structure and content of the XML output.
* **`converter`**: The compiled executable program.
