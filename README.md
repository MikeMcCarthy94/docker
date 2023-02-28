# docker

You can take your app and put it into a "Conatainer", using Docker. 

You can then install docker on any machine and it will be able to run that image.

The concept is similar to a virtual machine, but instead of emulating an entire computer we are just emulating the application.

#Download Docker
https://www.docker.com/

Download Docker desktop. 

Run it

Create a Dockerfile in your Python app project

FROM python:3

WORKDIR /usr/src/app USE THE DIRECTORY OF YOUR APP

COPY requirements.txt ./ YOU CAN MAKE A REQUIREMENTS FILE AND IT WILL DOWNLOAD ALL LIBRARIES AND WAHTEVER YOU NEED FOR PYTHON
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD [ "python", "./your-daemon-or-script.py" ]


Then run: docker build -t my-python-app .

Go to the docker desktop application 

On the left go to images

You can run this image and view the status in the containers/apps tab

This is using a prebuilt image. But we can modify this image to include any cron jobs that will start a job first thing

That job can run on loop creating processes, running async python code, running c++, modifying databases, etc...
