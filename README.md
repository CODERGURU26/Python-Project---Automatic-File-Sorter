# 📁 Automated File Sorter using Python

A simple yet powerful Python script that automatically organizes files in your directory by sorting them into categorized folders based on their file extensions.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![OS](https://img.shields.io/badge/OS-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

---

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [How It Works](#how-it-works)
- [Installation](#installation)
- [Usage](#usage)
- [Supported File Types](#supported-file-types)
- [Code Explanation](#code-explanation)
- [Customization](#customization)
- [Future Enhancements](#future-enhancements)
- [Prerequisites](#prerequisites)
- [Author](#author)

---

## 🎯 Project Overview

Tired of cluttered downloads folders and messy desktops? This automated file sorter is your solution! 

This Python project automatically scans a specified directory and organizes files into separate folders based on their file types. It uses Python's built-in `os` and `shutil` modules to create folders and move files efficiently.

**Perfect for:**
- 🗂️ Organizing cluttered download folders
- 📂 Cleaning up messy desktop directories
- 🎯 Automating repetitive file organization tasks
- 🚀 Improving workflow efficiency

---

## ✨ Features

- ✅ **Automatic Folder Creation**: Creates organized folders if they don't exist
- ✅ **Smart File Detection**: Identifies files by extension (.csv, .xlsx, .png, .jpg, .txt)
- ✅ **Duplicate Prevention**: Checks if file already exists before moving
- ✅ **Multiple File Types**: Supports CSV, Excel, images, and text files
- ✅ **Safe Operations**: Uses error prevention to avoid file conflicts
- ✅ **Easy Customization**: Simple to add more file categories
- ✅ **Jupyter Notebook Format**: Easy to run and modify

---

## 🔧 How It Works

1. **Scan Directory**: The script scans the specified directory for all files
2. **Create Folders**: Automatically creates category folders (csv files, image files, text files)
3. **Categorize Files**: Identifies each file's extension
4. **Move Files**: Moves files to their respective category folders
5. **Prevent Duplicates**: Checks if file already exists in destination folder

```
Before:                          After:
├── report.csv                   ├── csv files/
├── photo.png                    │   ├── report.csv
├── notes.txt                    │   └── data.xlsx
├── data.xlsx                    ├── image files/
├── screenshot.jpg               │   ├── photo.png
└── document.txt                 │   └── screenshot.jpg
                                 └── text files/
                                     ├── notes.txt
                                     └── document.txt
```

---

## 🚀 Installation

### Prerequisites
- Python 3.x installed on your system
- Jupyter Notebook (optional, for running .ipynb file)

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/CODERGURU26/Automated-File-Sorter.git
   cd Automated-File-Sorter
   ```

2. **No Additional Packages Required**
   - The script uses only built-in Python modules (`os` and `shutil`)
   - No pip installations needed!

3. **Open the Jupyter Notebook**
   ```bash
   jupyter notebook "Automated_File_Sorter_in_File_Explorer_using_Python.ipynb"
   ```

   Or run as a Python script (if converted to .py)

---

## 💻 Usage

### Method 1: Jupyter Notebook

1. Open the notebook file
2. Update the `path` variable with your target directory:
   ```python
   path = r"C:/Your/Target/Directory/"
   ```
3. Run all cells in sequence
4. Watch your files get organized automatically!

### Method 2: Python Script

If you convert the notebook to a Python script:

```bash
python file_sorter.py
```

### Quick Start Example

```python
import os, shutil

# Set your directory path
path = r"C:/Users/YourName/Downloads/"

# Run the script
# Files will automatically be organized into folders
```

---

## 📋 Supported File Types

| Category | Extensions | Folder Name |
|----------|-----------|-------------|
| **Spreadsheets** | `.csv`, `.xlsx` | `csv files` |
| **Images** | `.png`, `.jpg` | `image files` |
| **Text Documents** | `.txt` | `text files` |

---

## 🧩 Code Explanation

### 1. Import Required Modules
```python
import os, shutil
```
- `os`: For file system operations (checking paths, creating directories)
- `shutil`: For moving files between directories

### 2. Set Target Directory
```python
path = r"C:/Users/gs602/OneDrive/Desktop/Python Project - Automatic file sorter/"
```
- Uses raw string (`r""`) to handle Windows path backslashes

### 3. Get List of Files
```python
file_name = os.listdir(path)
```
- Retrieves all files and folders in the specified directory

### 4. Create Category Folders
```python
folder_name = ["csv files", "image files", "text files"]

for loops in range(0, 3):
    if not os.path.exists(path + folder_name[loops]):
        os.makedirs(path + folder_name[loops])
```
- Creates folders only if they don't already exist
- Prevents errors from attempting to create duplicate folders

### 5. Sort and Move Files
```python
for file in file_name:
    if (".csv" in file or ".xlsx" in file) and not os.path.exists(path + "csv files/" + file):
        shutil.move(path + file, path + "csv files/" + file)
    elif(".png" in file or ".jpg" in file) and not os.path.exists(path + "image files/" + file):
        shutil.move(path + file, path + "image files/" + file)
    elif ".txt" in file and not os.path.exists(path + "text files/" + file):
        shutil.move(path + file, path + "text files/" + file)
```
- Checks file extension
- Verifies file doesn't already exist in destination
- Moves file to appropriate folder

---

## 🎨 Customization

### Adding More File Types

Want to organize more file types? Simply extend the script:

```python
folder_name = ["csv files", "image files", "text files", "pdf files", "video files"]

# Add more conditions in the sorting loop
for file in file_name:
    # ... existing code ...
    elif ".pdf" in file and not os.path.exists(path + "pdf files/" + file):
        shutil.move(path + file, path + "pdf files/" + file)
    elif (".mp4" in file or ".avi" in file) and not os.path.exists(path + "video files/" + file):
        shutil.move(path + file, path + "video files/" + file)
```

### Common Extensions to Add

**Documents:**
```python
".doc", ".docx", ".pdf", ".ppt", ".pptx"
```

**Audio:**
```python
".mp3", ".wav", ".flac", ".aac"
```

**Video:**
```python
".mp4", ".avi", ".mkv", ".mov"
```

**Compressed:**
```python
".zip", ".rar", ".7z", ".tar"
```

**Code Files:**
```python
".py", ".js", ".html", ".css", ".java"
```

---

## 🔮 Future Enhancements

- [ ] Add GUI interface using Tkinter
- [ ] Implement automatic scheduling (run every X hours)
- [ ] Add undo functionality
- [ ] Create configuration file for custom rules
- [ ] Add logging to track all file movements
- [ ] Support for nested folder organization
- [ ] Add file size-based organization
- [ ] Implement date-based sorting
- [ ] Add support for regex patterns
- [ ] Create a system tray application
- [ ] Add email notifications after sorting
- [ ] Implement machine learning for smart categorization

---

## ⚙️ Prerequisites

- **Python Version**: 3.x or higher
- **Operating System**: Windows (can be modified for macOS/Linux)
- **Required Modules**: 
  - `os` (built-in)
  - `shutil` (built-in)
- **Optional**: Jupyter Notebook for .ipynb file

---

## 📝 Important Notes

### ⚠️ Safety Tips

1. **Test First**: Run on a test folder before using on important directories
2. **Backup**: Always backup important files before running automation scripts
3. **Path Verification**: Double-check the `path` variable before running
4. **Permissions**: Ensure you have read/write permissions for the target directory

### 🐛 Troubleshooting

**Issue**: Files not moving
- **Solution**: Check if you have write permissions for the directory

**Issue**: Script not finding files
- **Solution**: Verify the path is correct and uses proper format (`r"path"`)

**Issue**: Duplicate file errors
- **Solution**: The script already handles this, but ensure no files are currently open

---

## 📂 Project Structure

```
Automated-File-Sorter/
│
├── Automated_File_Sorter_in_File_Explorer_using_Python.ipynb
│   └── Main Jupyter Notebook with the sorting script
│
└── README.md
    └── Project documentation (this file)
```

---

## 🎓 Learning Outcomes

This project demonstrates:
- ✅ File system operations in Python
- ✅ Working with `os` and `shutil` modules
- ✅ Conditional logic and loops
- ✅ Error prevention techniques
- ✅ Practical automation scripting
- ✅ Directory management

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/NewFeature`)
3. Commit your changes (`git commit -m 'Add NewFeature'`)
4. Push to the branch (`git push origin feature/NewFeature`)
5. Open a Pull Request

**Ideas for Contributions:**
- Add support for more file types
- Create a GUI version
- Add scheduling functionality
- Improve error handling
- Add unit tests

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 📧 Contact & Connect

### Author

**Gururaj Krishna Sharma**

- 📧 Email: [guruuu2468@gmail.com](mailto:guruuu2468@gmail.com)
- 💼 LinkedIn: [Gururaj Krishna Sharma](https://www.linkedin.com/in/gururaj-krishna-sharma)
- 💻 GitHub: [@CODERGURU26](https://github.com/CODERGURU26)

---

## 🌟 Acknowledgments

- Python documentation for `os` and `shutil` modules
- Jupyter Notebook community
- Stack Overflow community for troubleshooting tips

---

## 🎯 Use Cases

### Personal Use
- Organize downloads folder automatically
- Clean up desktop regularly
- Sort project files by type

### Professional Use
- Organize client deliverables
- Sort incoming documents
- Maintain clean project directories

### Educational Use
- Learn Python file operations
- Understand automation concepts
- Practice scripting skills

---

## 📊 Performance

- **Speed**: Organizes 100+ files in seconds
- **Memory**: Minimal memory footprint
- **Efficiency**: Handles large directories without issues
- **Safety**: Built-in duplicate detection

---

**⭐ If you find this project helpful, please give it a star!**

---

*Last Updated: February 2026*
