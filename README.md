# Langchain's Autonomous Agent using AutoGPT

This Python script creates an autonomous agent using Langchain's AutoGPT. The agent uses a variety of tools to interact with data, perform web searches, process CSV files, scrape webpages, and run Python code.

## How It Works

The script begins by importing the necessary libraries and initializing the Language Model (LM) to be used (in this case, OpenAI's gpt-3.5-turbo).

Next, several tools are defined:

1. **Process CSV:** This tool reads a CSV file, creates a Pandas DataFrame, and executes instructions on the DataFrame. The instructions should be in natural language, not code. The results can be written to disk if an output path is specified.

2. **Web Search:** This tool uses the DuckDuckGo Search API to perform a web search and return the results as a JSON string.

3. **Browse Web Page:** This tool uses the Playwright library to load a webpage and BeautifulSoup to parse its content. It returns the text content of the webpage.

4. **Query Webpage:** This tool is an extension of the previous tool. It splits the scraped webpage text into smaller chunks and uses a question-answering model to answer a specified question using these chunks. It returns the answers from the model.

Finally, the autonomous agent is created using these tools, the Language Model, and a memory in the form of a vector store. The agent is then run based on a goal provided by the user.

## Usage

Before running the script, ensure that you have installed the required libraries, which include:

- `langchain`
- `pandas`
- `nest_asyncio`
- `asyncio`
- `faiss`
- `beautifulsoup4`
- `playwright`
- `pydantic`
- `duckduckgo_search`

You can install these using pip:

```bash
pip install langchain pandas nest_asyncio asyncio faiss-cpu beautifulsoup4 playwright pydantic duckduckgo_search
```

Also, make sure to install the Playwright dependencies with:

```bash
python -m playwright install
```

Then, you can simply run the script in a Python environment. When prompted, provide a goal in natural language.

## Future Improvements

Future improvements could include adding more tools, improving the interface for providing goals, and enhancing error handling.

## Disclaimer

This script is for educational purposes only. Always respect the rights of the content creators. Do not use it to scrape copyrighted content without permission.
