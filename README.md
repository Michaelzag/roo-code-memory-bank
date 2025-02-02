# Roo Code Memory Bank

## Maintain Project Context Across Sessions and Memory Resets

This repository contains the Memory Bank for the Roo Code project, designed to maintain project context across sessions and memory resets. 

**Documentation**

- [User Guide](docs/user-guide.md): Comprehensive guide on using the Roo Code Memory Bank system.

**Custom Instructions**

- [Custom Instructions](custom-instructions/): Directory containing custom instructions for different modes (Architect, Code, Ask) to enhance Roo Code's functionality within this project.

**Key Features**

- **Persistent Project Context:** Ensures Roo Code retains project knowledge across sessions.
- **Organized Documentation:** User guide and instruction modules for easy reference.
- **GitHub Synchronization:** настроено для синхронизации только необходимых файлов, таких как документация и пользовательские инструкции.

**Getting Started**

Refer to the [User Guide](docs/user-guide.md) for detailed setup and usage instructions.

**Repository Structure**

```
roo-code-memory-bank/
├── custom-instructions/
│   ├── global-instructions.md
│   ├── mode-arch.md
│   ├── mode-ask.md
│   ├── mode-code.md
│   ├── role-arch.md
│   ├── role-ask.md
│   └── role-code.md
├── docs/
│   └── user-guide.md
├── memory-bank/ # Excluded from Git (local memory bank)
└── .gitignore 
```

**License**

[License information here]
