# Image Renaming Script

This PowerShell script is designed to batch rename `.jpg` files within a specified folder, applying a sequential naming convention. The script processes all `.jpg` files in the folder and renames them using an `Image_` prefix followed by a three-digit sequence number (e.g., `Image_001.jpg`). If a file with the new name already exists, the script appends a suffix (`_n`) to the filename to ensure uniqueness.

## Features

- **Sequential Renaming**: The script renames each `.jpg` file in the folder with a sequentially numbered name, formatted as `Image_001.jpg`, `Image_002.jpg`, etc., ensuring that the sequence number is always three digits.
- **Sorted by Last Modified Time**: The images are renamed in order of their last modified date and time, with the oldest image being renamed first.
- **Conflict Handling**: If a file with the intended new name already exists, the script appends a suffix (`_1`, `_2`, etc.) to avoid overwriting files.
- **User-Friendly**: If the `-Path` parameter is not provided when running the script, it prompts the user to input the folder path.

## Usage

1. **Specify Folder Path**: You can either provide the folder path as a parameter when running the script or allow the script to prompt you for it.
2. **Run the Script**: The script will rename all `.jpg` files in the specified folder using the `Image_` prefix and sequence numbers.
3. **Conflict Resolution**: The script checks for existing files with the same name and adds a suffix to prevent overwriting.

### Example

To rename files in a folder located at `C:\Images`, you can run the script as follows:

```powershell
.\RenameImages.ps1 -Path "C:\Images"
```

If the `-Path` parameter is omitted, the script will prompt you to enter the folder path.

## Security Settings

To run this script securely, the PowerShell execution policy should be set to `AllSigned`. This ensures that all scripts and configuration files are signed by a trusted publisher.

### How to Check the Current Execution Policy

You can check your current PowerShell execution policy by running the following command in a PowerShell window:

```powershell
Get-ExecutionPolicy
```

If it returns something other than `AllSigned`, you should change it.

## How to Set the Execution Policy to AllSigned

To set the execution policy to `AllSigned`, run the following command in PowerShell:

```powershell
Set-ExecutionPolicy AllSigned -Scope CurrentUser
```
