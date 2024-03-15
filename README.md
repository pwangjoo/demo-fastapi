# README.md
FastAPI starting guide for MacOS (M1).

## Preparation
### 1. Using `pyenv`
```zsh
% brew install pyenv #Homebrew installation
% pyenv versions #check installed version & current version
% pyenv install [VERSION] #latest 3.12.2 (on 24/03/14)
% pyenv uninstall [VERSION] #uninstall
% pyenv global [VERSION] #set global python
% pyenv local [VERSION] #set local python (genrates .python-version file)
```
### 2. Using `venv`
```zsh
% python -m venv .venv #generate virtual environment
% source .venv/bin/activate #activate
(.venv) % deactivate #deactivate
```
Auto activation on VSCode
  1. Install VSCode Python package.
  1. `cmd`+`shift`+`p` > select Python: Select Interpreter

## Installation
```zsh
(.venv) % pip install fastapi
(.venv) % pip install "uvicorn[standard]"
```

## Initializing
### 1. Add `main.py`
```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def root():
    return {"message": "Hello World"}
```
### 2. Easy start with NodeMon
1. Add `package.json`.
    ```json
    {
      "config": {
        "port": 3000
      },
      "scripts": {
        "start": "uvicorn main:app --port $npm_package_config_port --reload",
        "prod": "uvicorn main:app --port $npm_package_config_port"
      }
    }
    ```

## Running
```zsh
% npm run start #start development server
```
