# Page-Stream-Segmentation-of-Business-Documents
Bachelor thesis project developing a PSS System with a multi-modal neural network. A sufficiently powerful Nvidia graphics card is needed to run the model. If not available refer to the Google Colab section.

## Run API
The API is available as a docker container. Docker has to be installed to use the container.
Run the following commands to start the API.

    docker build -t pss-business-documents .
    docker run -d -p 80:80 --name pss-api pss-business-documents


## Google Colab 
The API is also available as a Google Colab notebook.
Open the following link and follow the instructions in the notebook to run the API: 

https://colab.research.google.com/github/googlecolab/colabtools/blob/master/notebooks/colab-github-demo.ipynb

## Training and Testing
To retrain the model run the **training.py** script in the **models** folder.
For testing the model with use the **evaluate.py** script.

The dataset can be found at https://github.com/aldolipani/TABME in the **data** folder.
Run the **download_dataset.sh** file to download the train, validation and tests datasets and place them in the same folder as the training resp. evaluation script.

For the evaluation script the **test.csv** file in **predictions** is also needed. It is used for grouping documents into folders. Place it in the same folder as the script.
Use the **--clearcache** flag to reset the created cash file in both the training and evaluation script.

Run the scripts in the docker container or install the dependencies yourself.
The following commands work for Linux systems and were tested with Python 3.9:
    
    pip install -r requirements.txt
    apt-get -y install tesseract-ocr
    apt-get install poppler-utils -y