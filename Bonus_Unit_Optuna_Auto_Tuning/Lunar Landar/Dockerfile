FROM python:3.11-slim

WORKDIR /app

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y swig cmake python3-opengl ffmpeg xvfb g++ && \
    rm -rf /var/lib/apt/lists/* && \
    pip install --no-cache-dir setuptools==65.5.0 && \
    pip install --no-cache-dir -r https://raw.githubusercontent.com/huggingface/deep-rl-class/main/notebooks/unit1/requirements-unit1.txt && \
    pip install --no-cache-dir pyvirtualdisplay stable-baselines3 sb3-contrib jupyter optuna

# Make port 8888 available to the world outside this container
EXPOSE 8888

# Copy the current directory contents into the container at /app
COPY . .

# Run Jupyter Notebook when the container launches
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]