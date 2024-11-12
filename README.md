# File Compressor

This Rust program compresses a source file using Gzip compression and writes the compressed data to a target file. The program takes two command-line arguments: the path of the source file and the path of the target (output) file. It reports the original file size, the compressed file size, and the time taken for the compression process.

## Usage

Run the program with the following command:

```bash
cargo run -- <source> <target>

Arguments

    <source>: The path to the file you want to compress.
    <target>: The path where the compressed file should be saved.


    cargo run -- example.txt compressed.gz

    This command will read example.txt, compress it using Gzip, and save the result to compressed.gz.
Output

The program provides the following output:

    Source len: The size (in bytes) of the original file.
    Target len: The size (in bytes) of the compressed file.
    Elapsed: The time taken to complete the compression.




Source len: 1048576
Target len: 200836
Elapsed: 0.0325432s


Code Explanation

# Here's a breakdown of how the code works:

    Argument Check:
        Ensures that exactly two arguments (source and target) are provided.
        If not, it prints a usage message and exits.

    File Handling:
        Opens the source file and wraps it in a buffered reader.
        Creates the target file for saving compressed output.

    Compression:
        Uses GzEncoder with default compression to compress data from the source file.
        Records the start time for measuring compression duration.

    Copying and Finalizing:
        The copy function reads from the buffered input and writes to the encoder.
        Finalizes the encoder to ensure all data is written to the target file.

    Statistics Output:
        Prints the original file size, compressed file size, and time taken.

        Dependencies

This program requires the following dependencies:

    flate2: Provides Gzip compression.
    std::io: Provides file and stream handling utilities.
    std::time::Instant: Used for timing the compression operation.