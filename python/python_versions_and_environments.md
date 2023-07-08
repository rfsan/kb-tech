# Python versions and environments

- pipx
    - Install and run python applications in isolated environments
    - You must install pipx for every version of Python you install


## Unstructured notes

- Add the current directory to your virtual environment PYTHONPATH 

  ```bash
  echo "export PYTHONPATH=$PWD" >> $VIRTUAL_ENV/bin/activate
  ```