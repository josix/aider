## Aider Introduction Core Concepts

Here is the core concepts, and the basic ideas behind Aider I will be discussing in this presentation.

### Aider

- How to install Aider
- How to use Aider
- What features Aider provides
- How to apply Aider in your projects/daily life

### Aider Core Concepts

- How Aider works
- What is Repo Map and how Aider leverages it
- How Aider leverages Concrete Syntax Tree (CST)
- How Aider build prompts in the custom way (diff mode, etc.)

### LLM Related Concepts

- How Aider is designed as-is to be used with LLM
  - Aider come up with the idea of Repo Map and CST to do the better retrieval of the code
  - Aider designed its prompt templates to be used with LLM in a good way

### Experience with Aider

- Add the required-only files to the Aider workspace
- After using Aider for a while, what I have learned
  - Aider 近乎是結構化文字資訊的專家：
    - Code understanding：
      - 我將 Aider 視作 codebase 的 domain expert，詢問任何關於 codebase 的問題，利如詢問元件相依關係、執行流程圖或 high level 的架構都已經是了解一個新專案的起手式。這幫助了我了解 Airflow 的 codebase 幫助很多，甚至許多未解的 issue 我也是先詢問 Aider 以得到一些線索和靈感。(It only takes 10 NT dollars to save my day.)
      - 對於我的 digital garden （多數由 markdown 組成），Aider 可以直接成為我的代理人，這幾乎完全體現了所謂的第二大腦，我可以僅透過自然語言對話的方式，讓 Aider 幫我整理我的知識庫，回憶並且擴充這些資訊。
    - Documentation：
      - 同樣的，我也透過 Aider 產生許多的 sequence diagram 和 flowchart (through [mermaid.js](https://mermaid.js.org/))，在 PR 中附上這些圖表讓 reviewer 更容易理解我的設計和實作，完成這件事已經變得毫不費力。甚至是直接讓 Aider 產生出這份專案的 slides (through [marp](https://marp.app/))，對於快速擷取出重點也提升了很多效率。
    - Adding Unit Test：
      - 在不熟悉 codebase 的情況下，我時常是先開發功能而後再寫測試。透過 Aider 他同時瞭解了 codebase 上下文和使用的測試框架，可以寫出針對功能又符合 coding style 的測試，幾乎是符合原作者的寫法，相當驚艷。
  - 坊間的 AI assistant 開發工具多數專注於提供 auto-completion 和 code suggestion，Aider 在這之上更提供了開發者更需要的 **Code Maintenance** 的功能（包含 bug fixing, documenting, code understanding）以及完全與 Git、CLI、Programming Language 層級的整合，相當輕巧且功能強大。
    - 其他 AI assistant 工具對 codebase 熟悉度實在太低 retrieve 的資訊沒太多幫助，模仿可能沒什麼問題整理資訊並產出就不行了
  - Aider 對於 code understanding 有相當好的效果，工程師維護 legacy code 所花最多的時間是在看程式碼，因此程式的自我解釋程度越高越好，Aider 會是相當適合的工具，除了透過 chat 的方式與程式碼互動，建立 automation 的 workflow 讓程式碼可以自動化產生每次修正所產生 documentation （through PR 或 pre-commit）是可能的做法

- For designing LLM applications, we should focus on the following aspects:
  - How to design the prompt templates
  - How to design the retrieval of the codebase with better information quality
  - Choose the right LLM model

### Do's and Don'ts with Aider

- Ask the right questions, get the right answers; give the right commands, get the right results
  - If you knows what/where resources is helpful for you, add them to the prompts.
- Aider is doing well for code understanding, documentation, and code maintenance
- Aider is lightweight (no dependencies to IDE, no language server required), flexible, and powerful, we should build the LLM applications based on Aider's design principles

- Don't treat Aider as a search engine
  - Aider is not a search engine, it is more like a domain expert for your codebase. You should ask the right questions to get the right answers.
  - Don't ask Aider for the things it doesn't know
- Don't trust Aider blindly if you have no idea what you are asking
  - If you have no idea, ask Aider for help but don't trust it blindly. You should verify the answers by yourself and go back to the point 1.
