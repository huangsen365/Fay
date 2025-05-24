FROM python:3.12

# Set working directory
=======
# Set work directory
WORKDIR /app

# Copy project files
COPY . /app

# Install system and Python dependencies
RUN apt-get update -y && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        pkg-config wget cmake curl git vim build-essential \
        libgl1-mesa-glx portaudio19-dev libnss3 \
        libxcomposite1 libxrender1 libxrandr2 libqt5webkit5-dev \
        libxdamage1 libxtst6 && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    pip install --no-cache-dir -r docker/requirements.txt
=======
# Install Python dependencies
RUN pip install --no-cache-dir -r docker/requirements.txt

CMD ["python", "main.py"]

