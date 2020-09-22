# BUILD-USING docker build -f ./Dockerfile ../../ -t covid_visualize_serive
# RUN-USING: docker run -d -v --rm volume-name:/app/data

FROM python:3.8.5-slim-buster

# Install Python dependencies
COPY ./Docker/visualize_service/requirements.txt /app/
RUN pip3 install --no-cache-dir -r /app/requirements.txt

# Copy files
COPY ./src/visualization/visualize.py /app/
RUN chmod 755 /app/visualize.py

EXPOSE 8080

# Launch command
ENTRYPOINT ["python", "/app/visualize.py",  "--data_path",  "/app/data/"]