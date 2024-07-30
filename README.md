# Create Python Module for Distribution

### 1. Create Main Directory and Subdirectory

1. Open terminal or command prompt.
2. Navigate to location where you want to create your project directory.
3. Create main directory (replace `<main_directory>` with desired directory name):
    ```sh
    mkdir <main_directory>
    cd <main_directory>
    ```
4. Create subdirectory with same name as code file (replace `<code_file_name>` with desired code file name):
    ```sh
    mkdir <code_file_name>
    cd <code_file_name>
    ```

### 2. Place Code in Subdirectory

1. Create Python code file inside subdirectory (replace `<code_file_name>.py` with actual code file name):
    ```sh
    touch <code_file_name>.py
    ```

### 3. Create `__init__.py` File

1. Inside subdirectory, create `__init__.py` file:
    ```sh
    touch __init__.py
    ```
2. Open `__init__.py` and add all necessary imports from your code. For example:
    ```python
    from .<code_file_name> import *
    ```

### 4. Create `setup.py` File

1. Navigate back to main directory:
    ```sh
    cd ..
    ```
2. Create `setup.py` file:
    ```sh
    touch setup.py
    ```
3. Open `setup.py` and add the following content (replace placeholders with actual values):
    ```python
    from setuptools import setup, find_packages

    setup(
        name='<program_name>',
        version='<version_of_the_code>',
        packages=find_packages(),
        description='<description_of_what_the_package_is_doing>',
        author='<organization_or_person>',
        author_email='<email_of_creator>',
        install_requires=[
            # List your package dependencies here
            '',
        ],
    )
    ```

### 5. Install Required Packages

1. Open command prompt as an administrator.
2. Install `wheel` and `setuptools`:
    ```sh
    pip install wheel setuptools
    ```

### 6. Build Distribution

1. Change to main directory of code:
    ```sh
    cd <main_directory>
    ```
2. Run following command to build the distribution:
    ```sh
    python setup.py bdist_wheel
    ```

### 7. Verify Created Directories

After running the build command, you should see the following directories in your main directory:
- `build`
- `dist`
- `<projectname>.egg-info`

### Possible Errors and Solutions

- **ModuleNotFoundError**: If you encounter an error like `ModuleNotFoundError: No module named [package_name]`, ensure that the package is installed in your Python environment. You can verify with:
    ```sh
    pip show [package_name]
    ```

Congrats! You've structured a Python project for distribution!
