def modify_and_write_file(input_filename, output_filename):
    """
    Reads each line from an input file, adds a prefix, and writes
    the modified lines to a new output file.
    Handles FileNotFoundError and IOError.
    """
    try:
        with open(input_filename, 'r') as infile, open(output_filename, 'w') as outfile:
            line_number = 1
            for line in infile:
                modified_line = f"Line {line_number}: {line.strip()}\n"
                outfile.write(modified_line)
                line_number += 1
        print(f"Successfully read '{input_filename}', modified, and wrote to '{output_filename}'.")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found in the current directory.")
    except IOError:
        print(f"Error: Could not read from or write to the file(s). Please check permissions.")

if __name__ == "__main__":
    input_file = input("Enter the name of the file you want to read: ")
    output_file = "modified_" + input_file

    modify_and_write_file(input_file, output_file)

    print("\nProgram finished.")
    print(f"Running from Kitengela, Kajiado County, Kenya at {datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S %Z%z')}")
