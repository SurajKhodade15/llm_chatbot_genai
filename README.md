# LLM Chatbot with GenAI 🤖

A comprehensive tutorial and implementation of a production-ready chatbot using LangChain, Groq, and various LLM providers. This project demonstrates the complete journey from basic LLM interactions to enterprise-grade chatbot development.

## 🌟 Features

### Core Functionality
- **Multi-Provider LLM Support**: Integration with Groq, OpenAI, HuggingFace, and other providers
- **Session-Based Memory**: Persistent conversation history with session isolation
- **Multi-User Support**: Separate conversation contexts for different users
- **Dynamic Prompt Templates**: Flexible system instructions and behavior customization
- **Multi-Language Support**: Dynamic language switching during conversations
- **Automatic History Management**: Context window optimization with intelligent trimming

### Advanced Capabilities
- **Production-Ready Architecture**: Enterprise-grade patterns and best practices
- **Environment Security**: Secure API key management using environment variables
- **Conversation Isolation**: Complete session separation for multi-user applications
- **Memory Optimization**: Automatic conversation trimming to prevent context overflow
- **Cost Management**: Token usage optimization for production deployment

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Jupyter Notebook or VS Code with Jupyter extension
- API keys for your chosen LLM providers

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/SurajKhodade15/llm_chatbot_genai.git
   cd llm_chatbot_genai
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the project root:
   ```env
   # Required for Groq integration
   GROQ_API_KEY=your_groq_api_key_here
   
   # Optional: Other LLM providers
   OPENAI_API_KEY=your_openai_key_here
   LANGCHAIN_API_KEY=your_langchain_key_here
   LANGCHAIN_PROJECT=your_project_name
   HF_TOKEN=your_huggingface_token
   ```

4. **Launch the notebook**
   ```bash
   jupyter notebook 1-chatbots.ipynb
   ```

## 📚 Project Structure

```
llm_chatbot_genai/
├── 1-chatbots.ipynb       # Main tutorial notebook
├── requirements.txt       # Python dependencies
├── .env                  # Environment variables (create this)
├── .gitignore           # Git ignore file
└── README.md            # This file
```

## 🔧 Technologies Used

### Core Libraries
- **LangChain**: Framework for building LLM applications
- **LangChain Community**: Additional integrations and utilities
- **LangChain Groq**: Groq LLM provider integration
- **python-dotenv**: Environment variable management

### LLM Providers
- **Groq**: Fast inference for open-source models (Primary)
- **OpenAI**: GPT models integration
- **HuggingFace**: Open-source model ecosystem

### Supporting Libraries
- **Pandas**: Data manipulation and analysis
- **ChromaDB**: Vector database for embeddings
- **FAISS**: Efficient similarity search
- **BeautifulSoup4**: Web scraping capabilities
- **PyMuPDF**: PDF processing
- **Wikipedia**: Wikipedia data access

## 📖 Tutorial Overview

The notebook covers the following progression:

### 1. Basic Setup (Cells 1-3)
- Environment variable configuration
- LLM model initialization
- Basic message interaction

### 2. Conversation Memory (Cells 4-8)
- Implementing persistent conversation history
- Session management and isolation
- Multi-user support demonstration

### 3. Prompt Engineering (Cells 9-12)
- Dynamic prompt templates
- System instruction customization
- Structured conversation design

### 4. Advanced Features (Cells 13-17)
- Multi-language support
- Complex input parameter handling
- Production-ready integration

### 5. Production Optimization (Cells 18-22)
- Conversation history trimming
- Context window management
- Enterprise-grade architecture

## 🎯 Key Learning Objectives

By completing this tutorial, you will learn:

1. **LLM Integration**: How to connect and use different LLM providers
2. **Memory Management**: Implementing conversation persistence and recall
3. **Session Handling**: Building multi-user chatbot applications
4. **Prompt Engineering**: Creating effective system instructions
5. **Production Deployment**: Optimizing for real-world usage
6. **Security Practices**: Managing API keys and sensitive data
7. **Cost Optimization**: Controlling token usage and API costs

## 🛠️ Usage Examples

### Basic Chatbot
```python
from langchain_groq import ChatGroq
from langchain_core.messages import HumanMessage

model = ChatGroq(model="Gemma2-9b-It", groq_api_key=groq_api_key)
response = model.invoke([HumanMessage(content="Hello, I'm a developer!")])
```

### Chatbot with Memory
```python
from langchain_community.chat_message_histories import ChatMessageHistory
from langchain_core.runnables.history import RunnableWithMessageHistory

with_memory = RunnableWithMessageHistory(model, get_session_history)
response = with_memory.invoke(
    [HumanMessage(content="Remember, my name is John")],
    config={"configurable": {"session_id": "user123"}}
)
```

### Multi-Language Support
```python
from langchain_core.prompts import ChatPromptTemplate

prompt = ChatPromptTemplate.from_messages([
    ("system", "You are a helpful assistant. Answer in {language}."),
    MessagesPlaceholder(variable_name="messages"),
])

response = chain.invoke({
    "messages": [HumanMessage(content="Hello!")],
    "language": "Spanish"
})
```

## 🔒 Security Considerations

- **API Keys**: Never commit API keys to version control
- **Environment Variables**: Use `.env` files for local development
- **Production Secrets**: Use secure secret management in production
- **Session Isolation**: Ensure proper user data separation
- **Input Validation**: Sanitize user inputs before processing

## 📊 Performance Optimization

### Memory Management
- Implement conversation trimming for long chats
- Use appropriate `max_tokens` settings
- Monitor token usage for cost control

### Response Time
- Choose optimal model sizes for your use case
- Implement caching for frequently asked questions
- Use streaming responses for better user experience

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Setup
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **LangChain Team**: For the excellent framework
- **Groq**: For fast and efficient LLM inference
- **Google**: For the Gemma2 model
- **Open Source Community**: For the various supporting libraries

## 📞 Support

If you have any questions or run into issues:

1. Check the [Issues](https://github.com/SurajKhodade15/llm_chatbot_genai/issues) page
2. Create a new issue with detailed information
3. Join our community discussions

## 🔗 Related Projects

- [LangChain Documentation](https://python.langchain.com/)
- [Groq Documentation](https://groq.com/)
- [OpenAI API Reference](https://platform.openai.com/docs)

## 📈 Roadmap

- [ ] Add RAG (Retrieval Augmented Generation) capabilities
- [ ] Implement agent-based chatbots
- [ ] Add voice interaction features
- [ ] Create web interface deployment guide
- [ ] Add evaluation metrics and testing framework
- [ ] Implement conversation analytics

---

⭐ **If you found this project helpful, please give it a star!** ⭐

*Built with ❤️ by [Suraj Khodade](https://github.com/SurajKhodade15)*
