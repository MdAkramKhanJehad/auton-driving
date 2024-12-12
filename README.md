# auton-driving

## Target Program: OpenPilot

- **Program Name**: OpenPilot
- **Version Analyzed**: 0.9.7
- **Description**: OpenPilot is an open-source advanced driver assistance system (ADAS) developed by Comma.ai. It provides features such as adaptive cruise control, lane centering, and forward collision warnings, enabling semi-autonomous driving capabilities in supported vehicles. OpenPilot is built to work with various car models and is one of the most popular open-source projects in the autonomous driving space.

## Tools Used for Analysis

### 1. **Semgrep**

- **Version Used**: 1.99.0
- **Description**: Semgrep is a fast and flexible static code analysis tool.
- **More Information**:  
  Visit the [Semgrep GitHub Repository](https://github.com/semgrep/semgrep) for more details.

### 2. **Horusec**

- **Version Used**: 2.9.0-beta.3
- **Description**: Horusec is a comprehensive static application security testing tool designed to identify vulnerabilities in source code. 
- **More Information**:  
  Visit the [Horusec GitHub Repository](https://github.com/ZupIT/horusec) for more details.

#### Running Horusec
The following commands were used to run Horusec for analyzing the OpenPilot codebase:

```bash
image="horuszup/horusec-cli:v2.9.0-beta.3"; \
docker pull $image ;\
docker run --rm \
        -v /var/run/docker.sock:/var/run/docker.sock \
        -v $(pwd):/src/horusec $image horusec start \
        -p /src/horusec --information-severity=true  -P $(pwd)
