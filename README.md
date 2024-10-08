# FastAPI Toolkit 

FastAPI Toolkit is a set of tools to enhance the development of applications with FastAPI. It includes middleware for logging, request rate limiting, and more.

## Installation

You can install the package using pip:

  

```bash

pip  install  zetta-backend-toolkit

```

### Logger Middleware

To use the logging middleware, simply add it to your FastAPI application:

  

```python
from fastapi import FastAPI
from zetta-backend-toolkit.logger_middleware import LoggerMiddleware

app = FastAPI()

app.add_middleware(LoggerMiddleware)

@app.get("/")
async def read_root():
	return {"message": "Hello World"}

```

  

### Rate Limiting Middleware

To limit the number of requests per IP:

  

```python
from fastapi import FastAPI
from zetta-backend-toolkit.rate_limit_middleware import RateLimitMiddleware

app = FastAPI()

app.add_middleware(RateLimitMiddleware, max_requests=5, period=60)

@app.get("/")
async def read_root():
	return {"message": "Hello World"}

```
### Translation  Middleware

To translate requests and responses using googletrans: 
```python
from fastapi import FastAPI, Request
from zetta-backend-toolkit.translation_middleware import TranslationMiddleware

app = FastAPI()

app.add_middleware(TranslationMiddleware, target_language="en")

@app.post("/translate")
async def translate_text(request: Request):
    body = await request.body()
    return {"translated_text": body.decode("utf-8")}
```

Project Information

Name: fastapi-toolkit

Version: 0.1.0

Author: Gonzalo Geraci

Author's Email: gonza.geraci@gmail.com

Description: A Backend toolkit for FastAPI

Project URL: https://github.com/gonzageraci/FastAPI-toolkit

Requires Python: >=3.10

Dependencies:

- fastapi
  

### Contribute

Contributions are welcome. Please open an issue or a pull request on the GitHub repository.

  

### License

This project is licensed under the MIT License. See the LICENSE file for more details.

  

Contact

Author: Gonzalo Geraci

Email: gonza.geraci@gmail.com

GitHub: https://www.github.com/gonzageraci