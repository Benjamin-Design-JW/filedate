## Description 📝
Simple, convenient and cross-platform file date changing library. 📅

Forked from https://github.com/kubinka0505/filedate
- Support for MacOS in File.set(created)


## Installation 🖥️

```bash
git clone https://github.com/benjamin-dcs/filedate
cd filedate
python setup.py install
```

## Usage 📝
```python
import filedate

# Create filedate object
File_Date = filedate.File("~/Desktop/File.txt")

# Get file date
File_Date.get()

# Set file date
File_Date.set(
	created="01.01.2000 12:00",
	modified="3:30PM 2001/02/02",
	accessed="3rd March 2002 20:00:30"
)
```

### Copy file dates from one to another 🔃
```python
from filedate.Utils import Copy
Copy("~/Desktop/Input.mp4", "~/Desktop/Output.mp4").all()
```

### **Keeping files dates** ⌛
```python
from pathlib import Path
from filedate import Utils

# Get all files in subdirectories (recursive!)
Files = []
for File in Path(".").glob("**/*"):
	Files.append(File)

# --- #

# Initialize `Keep` object
Dates = Utils.Keep(Files)

# Pick dates
Dates.pick()

# ... Do your stuff ...
#
# from os import system
# for File in Files:
#     system(f'optimize -i "{File}"')

# Drop dates
Dates.drop()
```

### **Set file dates based on its name** 📝
```python
from filedate.Utils import Name

# Sets creation date
Name("~/Downloads/20200919_134705.wav").created()

# Sets all file dates
Name("Recording_20010204_103503.mp3").all()
```
