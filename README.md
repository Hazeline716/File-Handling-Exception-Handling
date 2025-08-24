File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
def modify_file(input_filename, output_filename):
    try:
        # Open the input file in read mode
        with open(input_filename, 'r') as input_file:
            # Read the content of the input file
            content = input_file.read()

        # Modify the content (for example, convert to uppercase)
        modified_content = content.upper()

        # Open the output file in write mode
        with open(output_filename, 'w') as output_file:
            # Write the modified content to the output file
            output_file.write(modified_content)

        print(f"Modified content has been written to {output_filename}")

    except FileNotFoundError:
        print(f"File {input_filename} not found")
    except Exception as e:
        print(f"An error occurred: {e}")


        # Example usage
input_filename = 'input.txt'
output_filename = 'output.txt'
modify_file(input_filename, output_filename)
This program:

1. Reads the content of the input file.
2. Modifies the content (in this case, converts it to uppercase).
3. Writes the modified content to the output file.

Make sure to replace 'input.txt' and 'output.txt' with your actual file names. If the input file doesn't exist, the program will print an error message. If any other error occurs during the process, the program will also print an error message.


def open_file(filename):
    try:
        with open(filename, 'r') as file:
            content = file.read()
            print("File contents:")
            print(content)
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    except PermissionError:
        print(f"Error: You do not have permission to read '{filename}'.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

def main():
    filename = input("Enter the filename: ")
    if not filename.endswith('.txt'):
        filename += '.txt'
    open_file(filename)

if _name_ == "_main_":
    main()

    Error Handling Mechanisms:

- FileNotFoundError: Triggered when the specified file does not exist.
- PermissionError: Occurs when you lack permission to access the file.
- Exception: Catches any other unexpected errors.

How It Works:

1. The open_file function attempts to open the file in read mode ('r').
2. If successful, it reads and prints the file content.
3. If the file doesn't exist or can't be read, it catches the corresponding exception and prints an error message.
4. The main function prompts the user for a filename, appends .txt if needed, and calls open_file.
