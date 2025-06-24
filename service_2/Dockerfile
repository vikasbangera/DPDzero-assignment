FROM python:3.13-slim as builder

WORKDIR /app

# Install uv
RUN pip install uv

# Install Flask directly
RUN pip install flask

# Copy dependency files
COPY pyproject.toml .
COPY .python-version .

# Create virtual environment and install dependencies
RUN uv venv
RUN . .venv/bin/activate && uv pip install --no-cache .

# Runtime stage
FROM python:3.13-slim

WORKDIR /app

# Copy installed packages from builder
COPY --from=builder /usr/local/lib/python3.13/site-packages /usr/local/lib/python3.13/site-packages

# Copy application code
COPY app.py .

EXPOSE 8002

CMD ["python", "app.py"]