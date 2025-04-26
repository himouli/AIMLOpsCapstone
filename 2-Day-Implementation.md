https://claude.ai/share/26013222-227c-4022-8202-c64990e71cb7

# OpenStack Log Root Cause Analysis

A machine learning system for interactive root cause analysis of OpenStack infrastructure logs.

## Project Overview

This project develops an interactive root cause analysis (RCA) system using Generative AI to understand and explain incidents in OpenStack IT environments. The system analyzes system logs to detect anomalies and explain potential root causes interactively.

### Features

- Log preprocessing and anomaly detection for OpenStack infrastructure
- Interactive query system for root cause analysis
- Web interface for log exploration and analysis
- Containerized deployment for easy setup

## Development Setup

### Prerequisites

- Python 3.8+
- Git
- (Optional) Docker and Docker Compose

### Local Development Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/openstack-rca.git
   cd openstack-rca
   ```

2. Set up the development environment:
   ```bash
   make setup
   ```

3. Run tests to verify the setup:
   ```bash
   make test
   ```

### Using Docker for Development

1. Build the development container:
   ```bash
   docker build -t openstack-rca-dev -f docker/Dockerfile.dev .
   ```

2. Run the development container:
   ```bash
   docker run -it -v $(pwd):/app -p 8501:8501 openstack-rca-dev
   ```

## Using the Log Analyzer

### Processing Logs

Process a log file:

```bash
make analyze logfile=path/to/your/logfile.log
```

### Running the Web Interface

Start the Streamlit web interface:

```bash
streamlit run src/app.py
```

Then open your browser at http://localhost:8501

## Project Structure

```
openstack_rca_project/
├── .github/                      # GitHub Actions configuration
├── data/                         # Data files
├── notebooks/                    # Jupyter notebooks
├── src/                          # Source code
│   ├── data/                     # Data processing scripts
│   ├── models/                   # ML models
│   └── visualization/            # Visualization code
├── tests/                        # Test files
├── configs/                      # Configuration files
├── docker/                       # Docker configuration
```

## CI/CD Pipeline

This project uses GitHub Actions for continuous integration and deployment:

- **CI Pipeline**: Runs tests, linting, and code quality checks on every push and pull request
- **CD Pipeline**: Builds and pushes Docker images for tagged releases

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please make sure your code passes all tests and lint checks before submitting a pull request.

## License

[MIT License](LICENSE)
