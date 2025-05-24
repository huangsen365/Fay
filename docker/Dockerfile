FROM python:3.12

# Install system dependencies required for some Python packages
RUN apt-get update -y && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        build-essential pkg-config wget cmake curl git vim \
        libgl1-mesa-glx libnss3 portaudio19-dev libasound2-dev ffmpeg && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Set work directory
WORKDIR /app

# Copy project files
COPY . /app

# Install Python dependencies
RUN pip install --no-cache-dir -r docker/requirements.txt

CMD ["python", "main.py"]

