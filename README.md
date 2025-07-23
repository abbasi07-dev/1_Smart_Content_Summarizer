# Smart Content Summarizer API

A professional-grade content summarization API built with LangChain, OpenAI, and FastAPI. Perfect for freelance projects requiring intelligent text processing and summarization.

## Features

- 🚀 **Intelligent Summarization**: Leverages OpenAI GPT models through LangChain
- 🎯 **Customizable Output**: Control length, style, and focus areas
- 📝 **Multiple Content Types**: Optimized for articles, emails, reports, and more
- 🔒 **Production Ready**: Type validation, error handling, and CORS support
- 📖 **Auto Documentation**: Interactive API docs with Swagger UI

## Tech Stack

- **LangChain**: For LLM orchestration and prompt management
- **OpenAI API**: GPT-3.5/4 for content generation
- **FastAPI**: Modern, fast web framework
- **Poetry**: Dependency management
- **Pydantic**: Data validation

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/1_Smart_Content_Summarizer.git
   cd 1_Smart_Content_Summarizer
   ```

2. **Install Poetry** (if not already installed)
   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

3. **Install dependencies**
   ```bash
   poetry install
   ```

4. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env and add your OpenAI API key
   ```

## Usage

1. **Run the API server**
   ```bash
   poetry run uvicorn src.app:app --reload
   ```

2. **Access the API**
   - API Base URL: `http://localhost:8000`
   - Interactive Docs: `http://localhost:8000/docs`
   - ReDoc: `http://localhost:8000/redoc`

3. **Example Request**
   ```bash
   curl -X POST "http://localhost:8000/summarize" \
        -H "Content-Type: application/json" \
        -d '{
          "content": "Your long text here...",
          "content_type": "article",
          "summary_length": 100,
          "style": "professional",
          "focus_points": "main arguments and conclusions"
        }'
   ```

## API Endpoints

### POST /summarize
Generate a summary of the provided content.

**Request Body:**
- `content` (string, required): Text to summarize (50-50,000 characters)
- `content_type` (string): Type of content (article, email, report, etc.)
- `summary_length` (integer): Target word count (20-500)
- `style` (string): Writing style (professional, casual, technical, academic)
- `focus_points` (string): Specific aspects to emphasize

**Response:**
- `summary`: Generated summary
- `word_count`: Number of words in summary
- `char_count`: Number of characters in summary
- `parameters_used`: Parameters used for generation

## Testing

Run tests with:
```bash
poetry run pytest
```

## Use Cases

Perfect for:
- 📰 News aggregation platforms
- 📧 Email management tools
- 📚 Research paper summarization
- 💼 Business report processing
- 🎓 Educational content distillation

## License

MIT License - feel free to use in your projects!

## Author

[Your Name] - [Your GitHub Profile]

---

⭐ If you find this useful, please star the repository!
```