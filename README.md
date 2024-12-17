# AI_AGENTS

# Quantum Computing Research and Speech Writing System

This project demonstrates how to use the `crewai` library to manage tasks in a collaborative, AI-driven environment. The system is designed to assist in finding and summarizing promising research in the field of quantum computing and then generating a keynote speech based on that research.

## Requirements

- **Python 3.x**
- **crewai**
- **crewai_tools** (for integrating with external tools like SerperDevTool)
- **langchain_ibm** (for using IBM WatsonxLLM)
- **OS library** (to handle environment variables)

To install the required dependencies, use:

```bash
pip install crewai crewai_tools langchain_ibm
```

## Setup

1. **API Keys**: 
   - Obtain an API key for Watsonx (IBM Watson AI).
   - Obtain an API key for Serper (the search tool).

2. **Set environment variables**: 
   Add your Watsonx API key, Serper API key, and Watsonx project ID to your environment variables:

   ```bash
   export WATSONX_APIKEY=<YOUR WATSONX API KEY HERE>
   export SERPER_API_KEY=<YOUR SERPER API KEY HERE>
   ```

   Alternatively, you can add them directly into the script using `os.environ`.

## Project Overview

This project is composed of two primary tasks:
1. **Research Task**: A Senior AI Researcher agent searches the internet to find promising research in quantum computing using the Serper tool. It generates a summary of five key findings.
2. **Writing Task**: A Senior Speech Writer agent takes the summarized research and creates an engaging keynote speech on quantum computing.

### Key Components

- **LLMs**: 
  - `WatsonxLLM` is used to perform language modeling and function calling tasks.
  - `function_calling_llm` is a different model that helps in calling functions as part of the workflow.

- **Agents**: 
  - `researcher`: A quantum computing expert who researches promising AI advancements.
  - `writer`: A speech writer who takes research and turns it into an engaging keynote.

- **Tools**: 
  - `SerperDevTool`: Used to perform web searches for relevant research findings.

- **Tasks**: 
  - **Task 1**: The researcher searches and summarizes 5 pieces of quantum computing research.
  - **Task 2**: The writer creates a detailed keynote speech from the research.

## How to Use

1. **Modify the Environment Variables**:
   - Make sure to replace the placeholders for your Watsonx API Key, Serper API Key, and Watsonx project ID with actual values in the script.

2. **Run the Script**:
   After setting up the environment variables, simply run the script:

   ```bash
   python quantum_computing_research.py
   ```

3. **Review the Output**:
   The output of Task 1 will be written to a file named `task1output.txt`, which contains a summary of the research findings.
   The output of Task 2 will be written to a file named `task2output.txt`, containing the keynote speech.

## Notes

- Ensure you have an active connection to the IBM Watsonx API for the LLMs to work properly.
- This project can be further expanded by adding more tasks and agents for different use cases, such as data analysis or further research generation.

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.
