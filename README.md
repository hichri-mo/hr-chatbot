# hr-chatbot helps users improve their CVs

# Overview
Welcome to HR-chatbot, an AI assistant designed to revolutionize the way job seekers approach their resumes. Powered by Hugging Face and CrewAI, this project aims to provide valuable insights and feedback to enhance your resume and improve your chances of landing your dream job.

# Prerequisites

Python (version 3.8 or higher), 
Hugging Face Transformers library, 
CrewAI library, 
Gradio


# Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install bib.

```bash
pip install -q markitdown gradio
```
```bash
pip install -q crewai
```

# Usage
Retrive token

```bash
from google.colab import userdata
token = userdata.get('pro_token')
```

Import model and build the agent 

```bash
from crewai import Agent, Task, Crew, Process, LLM

huggingface_llm = LLM(
    model="huggingface/meta-llama/Llama-3.3-70B-Instruct",
    api_key=token,
)

agent = Agent(
    role="Resume Expert",
    goal="""Provide a comprehensive analysis of the resume, including:
    backstory="An AI assistant powered by Huggingface and crewai that helps job seekers gain insights about their resume",
    llm=huggingface_llm,
```

Build and launch the gradio app

```bash
demo = gr.Interface(
    inputs=["file","textbox"],
    outputs="markdown",
    fn=review,
    title="Resume Expert",
)
demo.launch(debug=True)
```

# Feedbak

Upload your resume or paste the content into the assistant's interface.

Receive instant feedback and insights about your resume.

# Exemple

<img width="960" alt="pdf_agent" src="https://github.com/user-attachments/assets/8e3a7895-1093-47bf-a655-b141862ca7ec" />
<img width="960" alt="Cp-agentp2" src="https://github.com/user-attachments/assets/18770441-54ac-4dc5-953f-722a9365b42a" />


