# Kafka and Flask Integration Project

This project demonstrates how to set up and run a local Kafka server and use it alongside a Flask application to handle streaming of latitude and longitude data in real-time. The project involves producing, consuming, and visualizing geospatial data using Kafka and Leaflet.js.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Homebrew** (for macOS users)
- **Java** (OpenJDK 11)
- **Apache Kafka**
- **Python 3.x** and `venv` (Python virtual environment)

### 1. Install Java

1. **Install Homebrew** (if it's not already installed):

    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

2. **Install OpenJDK 11** using Homebrew:

    ```bash
    brew install openjdk@11
    ```

### 2. Download and Set Up Apache Kafka

1. **Download Kafka** from the [official Kafka website](https://kafka.apache.org/downloads).

2. **Extract the downloaded files** to a directory of your choice.

### 3. Start Zookeeper and Kafka

In this project Kafka relies on Zookeeper to manage distributed configurations. Follow these steps to start Zookeeper and Kafka:

1. **Start Zookeeper** (in one terminal):

    ```bash
    bin/zookeeper-server-start.sh config/zookeeper.properties
    ```

2. **Start Kafka Server** (in another terminal):

    ```bash
    bin/kafka-server-start.sh config/server.properties
    ```

### 4. Set Up the Flask Application

1. **Create a Python Virtual Environment** (optional but recommended):

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

2. **Install the necessary Python packages**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Flask app**:

    ```bash
    python app.py
    ```

### 5. Create Kafka Topic

To create a new Kafka topic for your geospatial data:

```bash
bin/kafka-topics.sh --create --topic geodata_final123 --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
 ```

### 6. Running Producers on different terminals**

**Run First Producer** (in one terminal):

```python busdata1.py```

**Run Second Producer** (in second terminal):

```python busdata2.py```

**Run First Producer** (in third terminal):

```python busdata3.py```

