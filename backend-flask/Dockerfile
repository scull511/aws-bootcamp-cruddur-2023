FROM python:3.10-slim-buster

# Inside Container
# make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# this contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# first . means /backend-flask (outside container)
# second . means /backend-flask (inside container)
# we are able to use '.' because of the WORKDIR line above, we are currently in that folder
COPY . .

# Set Environment Variables
# Inside Container and will remain set while the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# Commandd - python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]