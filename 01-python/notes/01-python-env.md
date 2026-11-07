# PYTHON ENVIRONMENT & DEPENDENCY MANAGEMENT 

## Why Environment Management matters ?
Imagine you developed an ML model on your laptop. It works perfectly, but when you run it on another computer or production server, it crashes.

Why? Because the software versions, libraries or other requirements on both machines are different.

- **Environment Management** means maintaining the same software setup across machines. Exp: OS, Python Version, Installed tools, etc

- **Dependency Management** means ensuring all required libraries and their compatible versions are installed. Exp: PyTorch, NumPy, Pandas, etc

In simple words: What works on your laptop should also work on the production server.

## How python finds the packages ?
when you write (example) ```import tensorflow``` python searches the package in a fixed order.
1. **sys.modules** : it checks whether the package has already imported or not. if Imported, it saves time and do not import again.
2. **sys.path** : If not found in sys.modules, then search in below folders(path)
   - **current directory** : where the script/file is present
   - **PYTHONPATH** : an env variable where you can define path to extra folders
   - **standard libraries** : these are built-in libraries, come with python
   - **site-packages** : this is the location where 3rd party packages store e.g. ```pip install numpy```

<img width="1352" height="173" alt="image" src="https://github.com/user-attachments/assets/556db631-5488-43f7-bdd7-b284a700211c" />

## Global Vs Local Package Installation :-
**Global Installation** (Problematic)

  ```pip install tensorflow #Installs to the system```
  
**Local Installation** (Isolated)

```
python -m venv my-project-env
source my-project-env/bin/activate
pip install tensorflow  # Installs only for this environment
```

| Issues with global installation  | Benefits of isolation |
| -------------------------------  | --------------------- |
| same package versions for every project | Each project has independent versions  |
| Upgrading for one project breaks others | upgrading is easy  |
| Can't test with different versions | safe to experiment with different versions  |
| Risk of system Python corruption | No risk due to isolation  |
| Requires admin/sudo on many systems | No admin privileges needed  |
| Conflicts between project requirements |  clear/separate dependency per projects |



