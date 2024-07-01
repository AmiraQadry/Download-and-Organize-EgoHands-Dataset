# Download and Organize EgoHands Dataset
![](https://source.roboflow.com/5w20VzQObTXjJhTjq6kad9ubrm33/9ExkEYuMdWqL6NN63SBY/original.jpg)

This guide explains how to download and organize the EgoHands dataset using Bash and Python commands in a Jupyter notebook. The dataset will be downloaded, extracted, and reorganized into a more manageable structure.

## Prerequisites

Ensure you have the following packages installed in your environment:
- `requests`

You can install the `requests` package using pip if you haven't already:
```bash
pip install requests
```

## Steps

1. **Download the Dataset:**

   The EgoHands dataset can be downloaded using the `requests` library in Python. The dataset is provided as a ZIP file.

   ```python
   import requests

   # URL of the dataset
   url = 'http://vision.soic.indiana.edu/egohands_files/egohands_data.zip'

   # Make a request to the URL
   response = requests.get(url)
   with open('egohands_data.zip', 'wb') as file:
       file.write(response.content)
   
   print("Dataset downloaded successfully.")
   ```

2. **Extract the Dataset:**

   After downloading the ZIP file, use the `unzip` command to extract its contents.

   ```bash
   !unzip /content/egohands_data.zip -d /content/egohands_data
   ```

3. **Organize the Dataset:**

   Move the specific folder of interest to a desired location and remove the original ZIP file and extracted folder to clean up the workspace.

   ```bash
   !mv /content/egohands_data/_LABELLED_SAMPLES/PUZZLE_LIVINGROOM_H_S /content/PUZZLE_LIVINGROOM_H_S
   !rm -r /content/egohands_data.zip
   !rm -r /content/egohands_data
   print("Dataset organized successfully.")
   ```
