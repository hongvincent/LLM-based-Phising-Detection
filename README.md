# LLM-based-Phising-Detection
## Rough system diagram
![Rough system diagram](https://github.com/hongvincent/LLM-based-Phising-Detection/assets/114135756/3e8afc5f-44a7-4e0f-bef3-ba08d6f5d455)

## README.md (English)

### Smishing Detection Solution

This repository contains a smishing detection solution that uses FastAPI and the OpenAI GPT model.

#### Files & Description:

1. **llm_based_phishing_detection_solution.py**: 
   - Initializes the FastAPI web application.
   - Extracts URLs from the given SMS text and assesses if these URLs are malicious.
   - If a URL is deemed malicious or unknown, it forwards the URL to the OpenAI GPT model for deeper analysis.

#### Setting Up:

1. Install the necessary Python libraries:
   ```bash
   pip install fastapi uvicorn openai selenium beautifulsoup4
   ```
2. Run `llm_based_phishing_detection_solution.py` to start the FastAPI application:
   ```bash
   python llm_based_phishing_detection_solution.py
   ```

#### Features:

- Extract URLs from the given SMS text.
- Evaluate if a URL is malicious.
- Additional in-depth analysis using the OpenAI GPT model.

#### API Endpoints:

### 1. `/sms_analysis`

- **Method**: POST
- **Description**: Extracts and analyzes URLs from the provided SMS text.
- **Request Body**:
  ```json
  {
    "sms_text": "Content of the SMS message"
  }
  ```
- **Response**: 
  - A JSON object containing the analysis of the URLs and the response from the OpenAI GPT model.

### 2. `/llm`

- **Method**: POST
- **Description**: Extracts URLs from the provided SMS text and requests analysis from the OpenAI GPT model.
- **Request Body**:
  ```json
  {
    "sms_text": "Content of the SMS message"
  }
  ```
- **Response**: 
  - A JSON object containing the response from the OpenAI GPT model.

### 3. `/check-sms`

- **Method**: POST
- **Description**: Analyzes the provided SMS text for potential malicious URLs. If a URL is deemed malicious or unknown, the URL is further analyzed using the OpenAI GPT model.
- **Request Body**:
  ```json
  {
    "sms_text": "Content of the SMS message"
  }
  ```
- **Response**: 
  - A JSON object containing results of the evaluation and potential threat assessment.

## README.md (한국어)

### 스미싱 탐지 솔루션

이 저장소는 FastAPI 및 OpenAI GPT 모델을 활용한 스미싱 탐지 솔루션을 포함하고 있습니다.

#### 파일 & 설명:

1. **llm_based_phishing_detection_solution.py**: 
   - FastAPI 웹 애플리케이션을 설정합니다.
   - 주어진 SMS 텍스트에서 URL을 추출하고 이 URL이 악성인지 아닌지를 판단합니다.
   - URL이 악성 또는 알 수 없는 상태인 경우, 이 URL을 OpenAI GPT 모델에 전달하여 추가 분석을 수행합니다.

#### 설정 방법:

1. 필요한 Python 라이브러리 설치:
   ```bash
   pip install fastapi uvicorn openai selenium beautifulsoup4
   ```
2. `llm_based_phishing_detection_solution.py` 파일을 실행하여 FastAPI 애플리케이션을 시작합니다:
   ```bash
   python llm_based_phishing_detection_solution.py
   ```

#### 주요 기능:

- 주어진 SMS 텍스트에서 URL 추출.
- URL이 악성인지 아닌지를 판단.
- OpenAI GPT 모델을 활용한 추가 분석.

#### API 엔드포인트:

### 1. `/sms_analysis`

- **Method**: POST
- **Description**: 주어진 SMS 텍스트에서 URL을 추출하고 분석합니다.
- **Request Body**:
  ```json
  {
    "sms_text": "문자 메시지 내용"
  }
  ```
- **Response**: 
  - URL 분석 결과 및 OpenAI GPT 모델의 응답을 포함한 JSON 객체.

### 2. `/llm`

- **Method**: POST
- **Description**: 주어진 SMS 텍스트에서 URL을 추출하고 OpenAI GPT 모델에 분석을 요청합니다.
- **Request Body**:
  ```json
  {
    "sms_text": "문자 메시지 내용"
  }
  ```
- **Response**: 
  - OpenAI GPT 모델의 응답을 포함한 JSON 객체.

### 3. `/check-sms`

- **Method**: POST
- **Description**: 주어진 SMS 텍스트를 분석하여 잠재적인 악성 URL을 확인합니다. URL이 악성 또는 알 수 없는 상태라면, 해당 URL을 OpenAI GPT 모델로 추가 분석합니다.
- **Request Body**:
  ```json
  {
    "sms_text": "문자 메시지 내용"
  }
  ```
- **Response**: 
  - 평가 결과와 잠재적 위협 평가를 포함한 JSON 객체.
