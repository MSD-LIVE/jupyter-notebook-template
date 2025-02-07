# MSD-LIVE BLANK Notebook


This repo contains the Dockerfile to build the notebook image as well as the notebooks
used in the MSD-LIVE deployment. It will rebuild the image and redeploy the notebooks
whenever changes are pushed to the main branch.

**The data folder is too big, so we are not checking this into github. You will have
to pull from s3 if you want to test locally**

## Testing the notebook locally

1. Get the data

   ```bash
   # make sure you are in the jupyter-notebook-<<blank>> folder
   mkdir data
   cd data
   aws s3 cp s3://<<blank>>-notebook-bucket/data . --recursive

   ```

2. Start the notebook via docker compose
   ```bash
   # make sure you are in the jupyter-notebook-<<blank>> folder
   docker compose up
   ```

## Notebooks
At the end of the Dockerfile do
```bash
COPY notebooks /home/jovyan/notebooks
```