# Stage 1: Build environment
FROM python:3.10-slim AS builder

WORKDIR /app

# Install Flask into a separate folder
COPY requirements.txt .
RUN pip install --upgrade pip && pip install --target=/python-deps -r requirements.txt

COPY app /app

# Stage 2: Runtime
FROM gcr.io/distroless/python3

# Add the installed dependencies to the Python path
ENV PYTHONPATH=/python-deps

COPY --from=builder /python-deps /python-deps
COPY --from=builder /app /app

WORKDIR /app
CMD ["main.py"]
