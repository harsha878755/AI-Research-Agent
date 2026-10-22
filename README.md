# AI Research Assistant Agent

## **Project Overview**

The **AI Research Assistant Agent** is an AI-powered research tool built using LangChain and Claude. It helps users research topics by generating structured responses, summarizing information, collecting sources, and using external tools to support the research process.

The agent uses an LLM to understand user queries, decide when to use available tools, and return structured research results using Pydantic.

## **Features**

- **AI-Powered Research:** Generates informative responses to user queries.
- **Web Search:** Uses a search tool to find relevant information.
- **Wikipedia Integration:** Retrieves background information on research topics.
- **Structured Output:** Uses Pydantic to organize responses into a predefined schema.
- **Tool Calling:** Allows the AI agent to select and use tools when necessary.
- **Save Results:** Uses a custom tool to save research output.
- **Interactive Input:** Accepts research queries directly from the terminal.

## **Technologies Used**

- **Python**
- **LangChain**
- **Anthropic Claude API**
- **Pydantic**
- **python-dotenv**
- **LangChain Community Tools**

## **Project Structure**

```text
AI-Agent/
├── main.py          # Main research agent
├── tools.py         # Search, Wikipedia, and save tools
├── .env             # API key configuration
├── .gitignore       # Files excluded from Git
└── README.md        # Project documentation
```

## **Installation and Setup**

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd AI-Agent
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
pip install python-dotenv pydantic langchain langchain-core langchain-community langchain-anthropic langchain-openai
```

### 4. Configure the API Key

Create a `.env` file in the project root:

```dotenv
ANTHROPIC_API_KEY=your_anthropic_api_key
```

Replace the placeholder with your valid Anthropic API key.

**Note:** API access requires an eligible Anthropic account with sufficient API credits.

### 5. Run the Application

```bash
python main.py
```

Enter a research topic when prompted.

## **Example Usage**

**Input:**

```text
What can i help you research? Applications of Artificial Intelligence in Healthcare
```

**Expected Output Structure:**

```json
{
  "topic": "Applications of Artificial Intelligence in Healthcare",
  "summary": "AI is used in healthcare for medical imaging, clinical decision support, patient monitoring, and personalized treatment.",
  "sources": [
    "Relevant research or web sources"
  ],
  "tools_used": [
    "Search Tool",
    "Wikipedia Tool"
  ]
}
```

*The example is illustrative. Actual results depend on the query, available tools, model response, and source retrieval.*

## **Output Schema**

The application uses a Pydantic model to structure research responses.

| Field | Description |
|---|---|
| `topic` | The research topic |
| `summary` | A summary of the findings |
| `sources` | List of sources used |
| `tools_used` | Tools used during the research process |

## **How It Works**

1. The user enters a research query.
2. LangChain sends the query to Claude.
3. The agent determines whether available tools are needed.
4. Search and Wikipedia tools retrieve relevant information when invoked.
5. The save tool can store information when selected by the agent.
6. Pydantic validates and structures the response.
7. The final research result is displayed in the terminal.

## **Future Enhancements**

- Add a Streamlit or React-based user interface.
- Export research reports to PDF or Markdown.
- Add citation verification and source links.
- Store previous research sessions in a database.
- Support downloadable research reports.
- Add more search providers and research tools.

## **Security**

- Never commit API keys or secrets to GitHub.
- Add `.env` and `venv/` to `.gitignore`.
- Keep API keys private.
- Monitor API usage and credit consumption.

## **License**

This project is intended for educational and research purposes. Add a license file if you plan to distribute it publicly.

---

**Developed as a Python-based AI research assistant using LangChain and Claude.**
