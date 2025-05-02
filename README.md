# LLM Execution Notebook

This repository contains a Jupyter Notebook ([`LLM_Execution.ipynb`](LLM_Execution.ipynb)) designed to interact with large language models (LLMs) locally using the [Ollama](https://ollama.com/) platform.

## Functionality

The notebook provides a simple Python script that:

1.  **Verifies Ollama Server:** Checks if the Ollama server is running locally.
2.  **Interactive Prompting:** Allows the user to enter prompts in a loop.
3.  **Streaming Responses:** Sends the prompts to a specified Ollama model and displays the response in real-time as it's generated (streaming).
4.  **Model Selection:** Uses the `gemma3:4b-it-qat` model by default, but this can be easily changed in the script.
5.  **Error Handling:** Includes basic error handling for common issues like the Ollama server not running or the specified model not being available locally.

## Setup and Execution Instructions

**⚠️ Hardware Requirements:** Running large language models locally can be resource-intensive. You will generally need a machine with significant RAM (check model requirements) and potentially a dedicated GPU for optimal performance. If your local machine is not sufficient, consider using a GPU instances like those available on [AWS EC2](https://aws.amazon.com/ec2/instance-types/#Accelerated_Computing).

1.  **Install Ollama:**
    Follow the official instructions at [ollama.com](https://ollama.com/) or use the command provided in the original [README](/Users/dani/Desktop/LLM_Execution/README):
    ```bash
    curl -fsSL https://ollama.com/install.sh | sh
    ```

2.  **Run Ollama Server:**
    Before running the notebook, ensure the Ollama server is running in your terminal:
    ```bash
    ollama serve
    ```
    Keep this terminal window open while using the notebook.

3.  **Pull the LLM Model:**
    The notebook is configured to use `gemma3:4b-it-qat`. Download it using the Ollama CLI:
    ```bash
    ollama pull gemma3:4b-it-qat
    ```
    *Note: This model requires approximately 3.5 GiB of available system memory.* You can change the `MODEL_NAME` variable in the second code cell of the notebook to use a different model available through Ollama (e.g., `llama3`, `mistral`, `phi3`). Make sure to pull the desired model first using `ollama pull <model_name>`.

4.  **Run the Notebook:**
    *   Open the [`LLM_Execution.ipynb`](LLM_Execution.ipynb) file.
    *   Run the code cells sequentially.
    *   Type your prompt and press Enter. The model's response will stream below.
    *   Type `exit` and press Enter to exit the script.