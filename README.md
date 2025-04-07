# genAI


https://python.langchain.com/api_reference/

APIS RELATED INFORMATION

import pkgutil
import langchain

print("📦 Submodules inside langchain:\n")

for module_info in pkgutil.iter_modules(langchain.__path__, prefix="langchain."):
    print(f"🔹 {module_info.name}")


## 🧠 LangChain vs LangChain Core – API Cheat Sheet

| 📦 Module / Area              | 🧩 `langchain` (High-level)                       | ⚙️ `langchain_core` (Low-level/core)                  |
|------------------------------|--------------------------------------------------|------------------------------------------------------|
| **LLMs / Chat Models**       | `LLM`, `ChatOpenAI`, `LLMChain`                  | `BaseLanguageModel`, `BaseChatModel`                |
| **Chains**                   | `LLMChain`, `SequentialChain`, `TransformChain` | No chains (you build logic manually with runnables) |
| **Agents**                   | `initialize_agent`, `AgentExecutor`             | Just the base interfaces like `Runnable`            |
| **Tools**                    | `Tool`, `load_tools`, `tool` decorator          | No direct tool APIs (tool calling is in `langchain`)|
| **Prompts**                  | `PromptTemplate`, `ChatPromptTemplate`          | `BasePromptTemplate`, `PromptValue`, `ChatPromptValue` |
| **Memory**                   | `ConversationBufferMemory`, `CombinedMemory`    | No memory (manual state management)                 |
| **Retrievers**               | `SelfQueryRetriever`, `MultiQueryRetriever`     | Interfaces only (`BaseRetriever`)                   |
| **Document Loaders**         | `UnstructuredPDFLoader`, `TextLoader`           | Not available (use community package)               |
| **Output Parsers**           | `PydanticOutputParser`, `StructuredOutputParser`| `BaseOutputParser`, `StrOutputParser`               |
| **Runnables**                | Optional (used internally)                      | ✅ Core building block: `Runnable`, `RunnableMap`   |
| **Callbacks**                | `StdOutCallbackHandler`, `Tracer`               | `BaseCallbackHandler`, `CallbackManager`            |
| **Messages** (Chat)          | `AIMessage`, `HumanMessage`, `SystemMessage`    | ✅ `langchain_core.messages` defines them            |
| **Documents**                | `Document`                                      | `langchain_core.documents.Document`                 |
| **Schema**                   | Internal use                                    | `RunnableConfig`, `PromptValue`, `BaseMessage`      |
| **Utilities**                | `langchain.hub`, `load_chain`, integrations     | ❌ Not included in core                             |

---

### 🧭 Key Concept

| Layer | Description |
|-------|-------------|
| `langchain_core` | 💡 Low-level, minimal interfaces (build-it-yourself). |
| `langchain`      | 🚀 High-level features (chains, agents, tools).      |


















