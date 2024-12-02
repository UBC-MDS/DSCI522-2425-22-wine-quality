# Wine Chromatic Profile Classification
Authors: Farhan Bin Faisal, Daria Khon, Adrian Leung, Zhiwei Zhang

DSCI 522 (Data Science Workflows) Project

# About
Here we attempt to build a classification model to predict the class of wine (red or white) based on the physiochemical properties (e.g. acidity, sulphates, citric acid, etc.). We used logistic regression model for our predictions, with our classifier performing well on unseen data with 0.99 test score, misclassifying 15 out 1950 instances.
<br> <br>
The data set we used in this project was created by By P. Cortez, A. Cerdeira, Fernando Almeida, Telmo Matos, J. Reis. 2009 as part of Decision Support Systems publication, and is available on UCI Machine Learning Repository [here](https://archive.ics.uci.edu/dataset/186/wine+quality). 

# Report
The final report can be found [here](https://ubc-mds.github.io/DSCI522-2425-22-wine-chromatic-profile/).

# Dependencies
- [Docke](https://www.docker.com/)
- [Jupyter Lab](https://jupyter.org/)
- or [VS CODE with Jupyter Extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

# Usage
> Note: Docker Desktop is required for this workflow. Make sure it is installed and running before proceeding.
## Running the analysis

1. Clone this repository `git clone`
2. Enter the root project direcory on your local repository and run:  
    ```
    docker-compose down --rmi all --volumes
    docker-compose up
    ```
3. In the terminal, look for a URL that starts with http://127.0.0.1:8888/lab?token= (see sample terminal output below). Copy and paste that URL into your browser.
<img src="img/docker_instructions.png" width=600>

4. Run analysis by opening `analysis/analysis.ipynb` and under the "Kernel" menu click "Restart Kernel and Run All Cells...".

### Clean up

To shut down the container and clean up the resources, 
type `Cntrl` + `C` in the terminal
where you launched the container, and then type `docker compose rm`

## Developer notes

### Developer dependencies
- `conda` (version 23.9.0 or higher)
- `conda-lock` (version 2.5.7 or higher)

### Adding a new dependency

1. Add the dependency to the `environment.yml` file on a new branch.

2. Run `conda-lock -k explicit --file environment.yml -p linux-64` to update the `conda-linux-64.lock` file.

2. Re-build the Docker image locally to ensure it builds and runs properly.

3. Push the changes to GitHub. A new Docker
   image will be built and pushed to Docker Hub automatically.
   It will be tagged with the SHA for the commit that changed the file.

4. Update the `docker-compose.yml` file on your branch to use the new
   container image (make sure to update the tag specifically).

5. Send a pull request to merge the changes into the `main` branch. 

# References
Cortez P, Cerdeira A, Almeida F, Matos T, Reis J. Wine Quality [dataset]. 2009. UCI Machine Learning Repository. Available from: https://doi.org/10.24432/C56S3T.

