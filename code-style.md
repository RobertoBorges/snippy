# Code Style Guide

This document outlines the code style conventions and best practices for Python applications using Azure Functions, async/await patterns, logging, and error handling.

## Python Code Conventions

### Naming Conventions
- **Variables**: Use lowercase words separated by underscores. For example: `user_name`, `account_balance`.
- **Functions/Methods**: Similar to variable naming, use lowercase with underscores: `calculate_total`, `get_user_data`.
- **Classes**: Use CamelCase: `UserDataProcessor`, `AccountManager`.

### Code Organization
```python
class Calculator:
    def __init__(self):
        self.result = 0

    def add(self, x, y):
        return x + y
    
    def subtract(self, x, y):
        return x - y
    
    def multiply(self, x, y):
        return x * y
    
    def divide(self, x, y):
        if y == 0:
            raise ValueError('Cannot divide by zero')
        return x / y
```
- **Classes** should encapsulate related functionality and maintain state when necessary.
- **Methods** should be kept short and focused on a single responsibility.

### Documentation Standards
```python
def generate_code_style(chat_history: str = "", user_query: str = "") -> str:
    """
    Generates a code style guide using an AI agent.
    
    Args:
        chat_history: The chat history or session for context
        user_query: The user's query for code style analysis
    
    Returns:
        str: The generated code style guide in Markdown format
    """
    pass
```
- Use docstrings to describe the purpose and usage of classes, methods, and functions.
- Follow Google or NumPy style for docstrings.

## Azure Functions

### Async/Await
```python
async def example_async_function():
    await asyncio.sleep(1)
    return "This is an async example"
```
- Always use `async` with `await` for asynchronous operations.
- Use async capabilities when interacting with Azure services asynchronously for improved efficiency and responsiveness.

### Logging Practices
```python
import logging

logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)

logger.info("This is an info message")
logger.warning("This is a warning message")
logger.error("This is an error message")
```
- Initialize a logger for each module using `logging.getLogger(__name__)`.
- Set appropriate logging levels (`DEBUG`, `INFO`, `WARNING`, `ERROR`) to avoid verbose logs.
- Suppress excessive logs from third-party libraries (e.g., Azure SDK logs).

## Error Handling

### Best Practices
```python
try:
    result = calculator.divide(4, 0)
except ValueError as e:
    logger.error("Error occurred: %s", e)
```
- Use try-except blocks around code that can raise exceptions.
- Catch specific exceptions to handle them gracefully.
- Log important error information using the logger.

## Best Practices

- **Consistency**: Stick to one naming convention and file structure throughout the project.
- **Modularity**: Break problems into small pieces and implement them as functions and classes.
- **Readability**: Write clear, concise, and self-explanatory code with comments when necessary.

By adhering to these guidelines, you can ensure your codebase is organized, maintainable, and scalable.
