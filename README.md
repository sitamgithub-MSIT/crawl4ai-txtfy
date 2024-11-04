# PeekText - Convert web articles to plain text

This repository contains the application that develops a web application that extracts text from web articles. The application uses Crawl4AI to extract the markdown content from the web articles. The extracted content is then displayed on the web page after applying some cleaning. The service is wrapped in a Flask web application and containerized using Docker. Finally, the service is deployed on the Google Cloud Platform (GCP) using the Cloud Run service.

## Project Structure

The project is organized as follows:

- `assets/`: This directory contains screenshots of the web application for testing and cloud deployment.

- `src/`: This directory contains the source code for the project.

  - `services/`: This directory contains the code for Reader API calling and cleaning the extracted text.

    - `content_cleaner.py`: This file contains the code for cleaning the extracted content from the web articles.
    - `crawler.py`: This file contains the code for the Crawl4AI to extract the fit markdown content from the web articles.

  - `logger.py`: This file contains the code for logging during the application's execution.
  - `exception.py`: This file contains the custom exceptions used in the project.

- `static/`: This directory contains the web application's CSS stylesheet and JavaScript file.

  - `css/`: This directory contains the custom CSS stylesheet for the web application.
  - `js/`: This directory contains the JavaScript file for the web application.

- `templates/home.html`: This file contains the HTML code for the home page of the Flask web application.

- `test/`: This directory contains the pytest tests for the Flask web application.

  - `test_app.py`: This file contains the tests for the Flask web application using the `pytest`. It includes tests for both routes.

- `app.py`: This file contains the code for the Flask web application. It contains two routes: one for the home page and one for the generated text task.

- `.env.example`: This file contains the example environment variables for the Flask web application. It is used as a template for the actual `.env` file.
- `app.yaml`: This file contains the configuration for deploying the Flask app on Google Cloud Platform (GCP).
- `Dockerfile`: This file contains the instructions for building the Docker image for the project.
- `.dockerignore`: This file contains the files to be ignored by Docker.
- `.gcloudignore`: This file contains the files that Google Cloud will ignore.
- `.gitignore`: This file contains the files to be ignored by Git.
- `requirements.txt`: This file contains the list of Python dependencies for the project. It can install the dependencies using the `pip` package manager.
- `requirements_test.txt`: This file contains the Python dependencies for testing the project. It can install the dependencies using the `pip` package manager.
- `LICENSE`: This file contains the license information for the project.
- `README.md`: This file provides an overview of the project and its structure.

## Technologies Used

- **Python**: Python is used as the primary programming language for this project.
- **Crawl4AI**: Crawl4AI is used to extract the markdown content from the web articles.
- **Flask**: Flask is used to develop the web application.
- **Docker**: Docker is used to containerize the application.
- **Cloud Run**: Google Cloud Run deploys the containerized application.
- **Cloud Build**: Google Cloud Build sets up the CI/CD pipeline.

## Installation and Environment Setup

To install the required dependencies and set up the environment, follow these steps:

1. Clone the repository: `git clone https://github.com/sitamgithub-MSIT/PeekText.git`
2. Change the directory: `cd PeekText`
3. Create a virtual environment: `python -m venv tutorial-env`
4. Activate the virtual environment:
   - For Windows: `tutorial-env\Scripts\activate`
   - For Linux/Mac: `source tutorial-env/bin/activate`
5. Install the required dependencies: `pip install -r requirements.txt`
6. Run the Flask app: `python app.py`

Now, you can open your local host at port 5000 and see the web application running. If you would like more information, please refer to the Flask documentation [here](https://flask.palletsprojects.com/en/2.0.x/quickstart/#debug-mode).

## Deployment

**Containerization**: The project is containerized using Docker. The Docker image is built using the `Dockerfile` in the project's root directory. That configuration file contains the instructions for building the Docker image while deploying the service in the cloud. Currently, only Google Cloud Platform (GCP) is tested for docker image deployment. Other cloud platforms are not sure about the deployment. Also, one can run the docker image locally with their preferences and own configurations. For more follow the instructions in the blog post [here](https://dev.to/pavanbelagatti/a-step-by-step-guide-to-containerizing-and-deploying-machine-learning-models-with-docker-21al).

**Google Cloud Platform (GCP)**: The project is deployed on the Google Cloud Platform (GCP) using the Cloud Run service. The Docker image is deployed on the Cloud Run service. To deploy the service to Google Cloud, a very brief overview of some of the steps is provided below:

- Sign up for a Google Cloud account.
- Set up a project and enable the necessary APIs (Create a new project in the Google Cloud Console.
  Enable the required APIs, such as Cloud Run and Artifact Registry, through the Console.)
- Deploy the Docker image to Google Cloud Run. (Build and push your Docker image to the Google Artifact Registry or another container registry. Deploy the image to Cloud Run by specifying the necessary configurations.)
- Access the service using the provided URL. (Once deployed, a URL is provided to access the service. Use the URL to access the service.)

For detailed instructions and code examples, please review the blog post [here](https://lesliemwubbel.com/setting-up-a-flask-app-and-deploying-it-via-google-cloud/). The blog post should be enough to get you started with deploying this on GCP. Also, please take a look at the screenshots in the assets folder for this project's deployment results.

## Testing

To test the deployed service locally, follow these steps:

1. Check the `test/` directory for the test files.
2. Assuming you have your virtual environment activated, install the dependencies for testing: `pip install -r requirements_test.txt`
3. Run the `test_app.py` file to test the Flask app.
4. Execute the command: `pytest test/test_app.py`
5. Verify the response and check for any errors or issues.
6. Optionally, please take a look at the screenshots in the assets folder for test results.

## Usage

Once the Flask web application is up and running, it allows users to provide a URL of a web article and extract the text from the article. To use the web application, follow these steps:

1. Run the Flask app: `python app.py`
2. Open a web browser and go to `http://localhost:5000/`
3. Provide web article URLs in the text box.
4. Click the "CONVERT" button.
5. The extracted text will be displayed then.

## Results

The project successfully extracts text from web articles. The extracted text is displayed on the web page after applying some cleaning. For results, refer to the `assets/` directory for the output screenshots, which show the web application's functionality and the deployment on Google Cloud Platform (GCP).

## Conclusion

In this project, we successfully developed an application that extracts text from web articles. We used Crawl4AI to extract the content from the web articles and then after applying some cleaning, we displayed the extracted text on the web page. Then we wrapped the service in a Flask web application and containerized it using Docker. Finally, we deployed it on the Google Cloud Platform (GCP) using the Cloud Run service.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact

If you have any questions or suggestions regarding the project, feel free to reach out to me on my [GitHub profile](https://github.com/sitamgithub-MSIT).

Happy coding!
