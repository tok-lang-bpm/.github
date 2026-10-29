# tok — process models as text

**tok** is a plain-text language for BPMN 2.0 process models with their DMN decisions, Camunda forms and simulation parameters. One short text file is the model; the tok engine checks it and produces BPMN 2.0 XML with a diagram layout, SVG, DMN 1.5, Camunda 8 forms, simulation results and event logs.

```
tok 1.0 "Book request"

pool library "Library"
  start need "Book needed"
  user order "Place an order"
  xor available "Available?"
  user lend "Lend the book"
  end lent "Book lent"
  end declined "Request declined"

flow need -> order -> available
flow available -> lend "yes"
flow available -> declined "no"
flow lend -> lent
```

| Start here | |
|---|---|
| [**The guide**](https://tok-lang-bpm.github.io/) | the language, the tools, the programming interfaces, AI agents and integrations, with examples and exercises |
| [**Playground**](https://tok-lang-bpm.github.io/playground/) | write a model in the browser and see its diagram; nothing to install |
| [**tok**](https://github.com/tok-lang-bpm/tok) | the language specification, the Rust engine, the packages for Python, R and Julia, the language server, the VS Code extension and the MCP server; [issues](https://github.com/tok-lang-bpm/tok/issues) |
| [**tok-agent**](https://github.com/tok-lang-bpm/tok-agent) | the skill and the MCP server for AI agents, as one plugin |
| [**setup-tok**](https://github.com/tok-lang-bpm/setup-tok) | GitHub Action that installs tok and checks the models of a repository |

| Install | |
|---|---|
| Python, command line, MCP server | `pip install tok-lang` |
| Rust | `cargo install tok-cli` |
| R | `install.packages("tokr")` |
| Julia | `Pkg.add(["Tok", "tok_jll"])` |
| VS Code | extension **tok** (`tok-lang-bpm.tok`) |
| AI agents | `/plugin marketplace add tok-lang-bpm/tok-agent` |
