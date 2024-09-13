# Dockerfile for book_catalog microservice

# First we use an official python image as a base image
FROM python:3.12-bookworm

# Then set the working directory as /app inside the container
WORKDIR /app/

# Copy requirments.txt from book_catalog directory to the working directory in the container
COPY book_catalog/requirements.txt .

# Run pip to install the required python dependencies which are listed in the requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# copy the whole book_catalog into the container's working directory
COPY /book_catalog/ .

# the command will run the uvicorn server with the main FastTAPI app
# the app will be hosted on 0.0.0.0:8000
CMD ["uvicorn","main:app","--host","0.0.0.0", "--port","8000"]