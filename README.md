# week5-python-assignment.py
def read_and_modify_file():
    try:
        # Step 1: Ask user for a filename
        filename = input("📄 Enter the filename to read from: ")

        # Step 2: Try opening and reading the file
        with open(filename, 'r') as file:
            content = file.read()

        # Step 3: Modify the content (Example: make all text uppercase)
        modified_content = content.upper()

        # Step 4: Define a new output filename
        new_filename = "modified_" + filename

        # Step 5: Write the modified content to the new file
        with open(new_filename, 'w') as new_file:
            new_file.write(modified_content)

        print(f"✅ Modified content has been written to '{new_filename}'.")

    except FileNotFoundError:
        print("❌ Error: The file was not found.")
    except PermissionError:
        print("❌ Error: You do not have permission to access the file.")
    except Exception as e:
        print(f"❌ Unexpected error: {e}")

# Run the program
read_and_modify_file()
