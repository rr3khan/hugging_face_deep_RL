FROM python:3.11

WORKDIR /app

RUN apt install swig cmake

RUN pip install -r https://raw.githubusercontent.com/huggingface/deep-rl-class/main/notebooks/unit1/requirements-unit1.txt && \
    sudo apt-get update && \
    apt install python-opengl && \
    apt install ffmpeg && \
    apt install xvfb && \
    pip3 install pyvirtualdisplay && \
    !pip install stable-baselines3 && \
    pip install sb3-contrib 

# Make port 8888 available to the world outside this container
EXPOSE 8888

# Copy the current directory contents into the container at /app
COPY . .

# Run Jupyter Notebook when the container launches
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]    