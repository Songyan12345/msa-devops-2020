# MSA-DevOps

This repository contains the URL for an Azure-hosted React website. Azure build and release pipelines have been set up for the website in conjunction with GitHub to enable continuous deployment. 

The Azure-hosted website can be found [here](https://msa-devops-s2020.azurewebsites.net/).

#### About:

* **The build pipeline** creates releases on new commits to the **master** and **develop** branches. It first builds the React application and archives it as a zip file. Then, it publishes the archive as a build artifact, ready to be deployed. The pipeline is set to run on new commits to both the **master** and **develop** branches as each modification of the application code should be actively reflected through the creation of a new build. This allows for ease of continuous testing and can notify developers of any bugs in a timely manner.

* **The release pipeline** deploys releases on new commmits to the **master** branch. Using the build artifact created by the build pipeline, the release pipeline deploys the React application to an Azure-hosted website, which can then be accessed by users using the website URL. The pipeline is set to run on new commits to only the **master** branch as deployments should only take place once the application is stable. In general, this would mean that sub-branches are merged into the **master** branch after a series of reviews, indicating that the code has been checked for bugs and is of a publishable condition. This means that the deployed application will have a smaller chance of containing serious bugs.
