# 2. Setting Up Python

## 2.1 Installing Python

### Guide through downloading Python from python.org
1. Open your web browser and navigate to https://www.python.org/downloads/
2. You'll see a big button to download the latest version of Python for your operating system. Click this button.
3. This will download an installer file. Once downloaded, run this file.

Installing Python:
- On Windows: Run the installer. Important: Check the box that says "Add Python to PATH" before clicking "Install Now".
- On macOS: Open the .pkg file and follow the installation wizard.
- On Linux: Many distributions come with Python pre-installed. If not, use your distribution's package manager (e.g., `sudo apt-get install python3` for Ubuntu).

### Explain the difference between Python 2 and Python 3
Python 3 is the current and future version of the language, while Python 2 reached its end of life in 2020.

Key differences:
1. Print function: In Python 2, `print` is a statement. In Python 3, it's a function.
   ```python
   # Python 2
   print "Hello, World!"

   # Python 3
   print("Hello, World!")
   ```

2. Division: In Python 2, division of integers returns an integer. In Python 3, it returns a float.
   ```python
   # Python 2
   print 3 / 2  # Output: 1

   # Python 3
   print(3 / 2)  # Output: 1.5
   ```

3. Unicode support: Python 3 has better Unicode support, which is important for handling non-ASCII text.

For this course and all new Python projects, use Python 3.

### Demonstrate how to verify the installation (python --version in command line)
1. Open a command prompt or terminal.
2. Type `python --version` and press Enter.
3. You should see output like `Python 3.x.x`, where x.x is the specific version number.

If you see an error message, it might mean Python isn't correctly added to your system's PATH. In this case, you may need to reinstall Python and ensure you check "Add Python to PATH" during installation.

## 2.2 Introduction to Jupyter Notebooks

### Explain what Jupyter Notebooks are and why they're useful for data science
Jupyter Notebooks are web-based interactive computing platforms that allow you to create and share documents containing live code, equations, visualisations, and narrative text.

Key features:
1. Interactive coding: You can write and run code in small, manageable chunks (cells).
2. Rich media output: Results can be displayed as text, images, videos, or interactive plots.
3. Markdown support: You can include formatted text, links, and images for documentation.

Benefits for data science:
1. Exploratory data analysis: Easily visualise and interact with data.
2. Reproducibility: Share entire workflows, including code, results, and explanations.
3. Storytelling: Create narratives around your data analysis process.

### Guide through installation of Jupyter (pip install jupyter)
1. Open a command prompt or terminal.
2. Type the following command and press Enter:
   ```
   pip install jupyter
   ```
3. Wait for the installation to complete. You'll see a progress bar and finally a success message.

Note: If `pip` isn't recognised, you may need to use `python -m pip install jupyter` instead.

### Demonstrate how to launch Jupyter Notebook (jupyter notebook command)
1. Open a command prompt or terminal.
2. Navigate to the directory where you want to create your notebook.
3. Type the following command and press Enter:
   ```
   jupyter notebook
   ```
4. This will start the Jupyter Notebook server and open a new tab in your default web browser.
5. You'll see the Jupyter dashboard, showing files in your current directory.

## 2.3 Writing and Running Your First Python Code

### Show how to create a new notebook
1. In the Jupyter dashboard, click the "New" button in the top right.
2. Select "Python 3" from the dropdown menu.
3. A new notebook will open in a new tab.

### Explain cells: code cells vs. markdown cells
Jupyter notebooks are composed of cells, which can be two main types:

1. Code cells:
   - Used for writing and running Python code.
   - To run, click the cell and press Shift+Enter or click the "Run" button.

2. Markdown cells:
   - Used for writing formatted text, including headers, lists, links, and even LaTeX equations.
   - To render, click the cell and press Shift+Enter or click the "Run" button.

To change cell type:
1. Click on a cell to select it.
2. Use the dropdown in the toolbar to change between "Code" and "Markdown".

### Write a simple "Hello, World!" program
1. In a code cell, type the following:
   ```python
   print("Hello, World!")
   ```
2. Run the cell (Shift+Enter or click "Run").
3. You should see the output "Hello, World!" below the cell.

### Demonstrate how to run a cell (Shift + Enter)
1. Click on a cell to select it.
2. Press Shift+Enter on your keyboard.
3. The cell will run, and the output (if any) will appear below the cell.
4. The focus will move to the next cell. If there isn't a next cell, a new one will be created.

Additional tips:
- Ctrl+Enter runs the current cell but keeps the focus on that cell.
- Alt+Enter runs the current cell and inserts a new cell below.

Practice:
1. Create a new code cell.
2. Write a simple calculation, like `2 + 2`.
3. Run the cell and observe the output.

Remember, Jupyter Notebooks autosave your work, but it's a good practice to manually save (File > Save and Checkpoint) periodically.