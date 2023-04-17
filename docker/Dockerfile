# Use an official Python base image from the Docker Hub
FROM python:3.11-slim

# Install git
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
COPY docker/sources.list /etc/apt/sources.list
RUN apt-get -y update
RUN apt-get -y install git chromium-driver

# Set environment variables
ENV PIP_NO_CACHE_DIR=yes \
    PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

# Create a non-root user and set permissions
RUN useradd --create-home appuser
WORKDIR /home/appuser
RUN chown appuser:appuser /home/appuser
USER appuser

# Copy the requirements.txt file and install the requirements
COPY --chown=appuser:appuser requirements-docker.txt .
RUN pip install --no-cache-dir --user -r requirements-docker.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/

# Copy the application files
COPY --chown=appuser:appuser autogpt/ ./autogpt

# Set the entrypoint
ENTRYPOINT ["python", "-m", "autogpt"]
