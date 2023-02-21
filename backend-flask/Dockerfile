FROM python:3.10-slim-buster
# Inside Container
# make a new folder inside container
WORKDIR /backend-flask
# From Outside of Container - >Inside Container
# this contains the libraires want to install to run the app 
COPY requirements.txt requirements.txt
# Inside Container
# install python libraries used for the app 
RUN pip3 install -r requirements.txt
# Outside Container -> Inside Container
# . means everything in the current directory
# first period. - /backend-flask (outside of container)
# second period. - /backend-flask (inside container)
COPY . .
# Set environment variables (Env Vars) inside container, will remain until container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
# python3 -m flask run --host=0.0.0.0 --port=4567 
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]