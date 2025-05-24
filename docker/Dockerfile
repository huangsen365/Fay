FROM python:3.12

# Set work directory
WORKDIR /app

# Copy project files
COPY . /app

# Install Python dependencies
RUN pip install --no-cache-dir -r docker/requirements.txt

CMD ["python", "main.py"]

