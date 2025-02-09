# LangChain Hello World Project using Google Gemini Flash 2.0

## Overview
This project demonstrates how to integrate **LangChain** with **Google Gemini Flash 2.0** to build a simple chatbot that answers user questions. It is developed using **Google Colab** and requires access to the Gemini API.

## Features
- Uses **LangChain** to manage prompts and responses.
- Integrates with **Google Gemini Flash 2.0**.
- Provides a structured pipeline for generating AI-powered responses.

## Prerequisites
Before running this project, ensure you have the following:

1. A **Google Colab** environment.
2. Python **3.9+** installed.
3. A **Google Gemini Flash API Key**.
4. Required Python dependencies installed.

## Installation
To install the required dependencies, run:

```bash
pip install --upgrade langchain langchain-community google-generativeai
```

## Project Setup
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up your **Gemini Flash API Key**:
   ```python
   import os
   os.environ["GEMINI_API_KEY"] = "your_api_key_here"
   ```

## Usage
Run the following Python script to test the chatbot:

```python
from langchain_google_genai import GoogleGenerativeAI
from langchain.prompts import PromptTemplate
from langchain.chains import LLMChain
import os

# Configure the Gemini Flash model
llm = GoogleGenerativeAI(
    api_key=os.getenv("GEMINI_API_KEY"),
    model="gemini-flash",
    temperature=0.7
)

# Create a prompt template
prompt_template = PromptTemplate(
    input_variables=["question"],
    template="You are a helpful assistant. Answer the following question:\n\n{question}"
)

# Create the LLM chain
chain = LLMChain(llm=llm, prompt=prompt_template)

# Run the chain with a sample question
question = "What is LangChain?"
response = chain.run({"question": question})

print("Answer:", response)
```

## Expected Output
```
Answer: LangChain is an open-source framework for building applications powered by large language models. It simplifies workflows, integrates tools, and supports multi-step chains and agents.
```

## Troubleshooting
If you encounter errors:
- Ensure all dependencies are installed using `pip install --upgrade langchain langchain-community google-generativeai`.
- Verify that your API key is correct and set up properly.
- Restart the runtime in Google Colab after installation.

## Contributing
Feel free to submit issues or pull requests to enhance this project.

## License
This project is licensed under the MIT License.



