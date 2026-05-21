# docker | Ollama


## Default configs

``` docker compose up -d --build ```

``` curl http://localhost:11434/api/tags ```


## Custom configs

``` HOST_ADDRESS=0.0.0.0 HOST_PORT=11435 MODEL_NAME=qwen3.5:0.8b docker compose up -d --build ```

``` curl http://localhost:11435/api/tags ```

## Simple Request

```
curl http://localhost:11434/api/generate \
  -H "Content-Type: application/json" \
  -d '{
    "model": "llama3.2:1b",
    "prompt": "Why is the sky blue?",
    "stream": false
  }'
```

## Simple Request with jq

```
curl http://localhost:11434/api/generate \
  -H "Content-Type: application/json" \
  -d '{
    "model": "llama3.2:1b",
    "prompt": "Why is the sky blue?",
    "stream": false
  }' | jq -r '.response'
```
