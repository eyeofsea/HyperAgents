FROM python:3.12-slim

# Prevent interactive prompts
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUTF8=1
ENV PYTHONIOENCODING=utf-8

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /hyperagents

# Copy requirements and install Python dependencies (core only)
COPY requirements_paper_review.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire repository
COPY . .

# Keep the container running
CMD ["tail", "-f", "/dev/null"]
