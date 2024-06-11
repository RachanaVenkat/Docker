FROM ubuntu:20.04

# Set working directory
WORKDIR /app

# Copy the requirements file and application code
COPY requirements.txt /app/
COPY devops /app/devops

# Set environment variables
ENV PIP_BREAK_SYSTEM_PACKAGES=1

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install --no-cache-dir -r requirements.txt && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Set the entry point and default command
ENTRYPOINT ["python3"]
CMD ["devops/manage.py", "runserver", "0.0.0.0:8000"]





