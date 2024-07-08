### Ollama with Docker 

```
docker run -it -v ollma:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

To use ollama cli in docker, run 

```
docker exec -it ollama bash
```

Check ollama version with `ollama -v`

My ollama version is `0.1.48`

metadata file inside `models/manifests/registry.ollama.ai/library` - `gemma/2b`

Test Prompt - `10*10`

Answer -

``` 
Sure. The given code is:

```python
10 * 10
```
<br>

Insted of mapping ./root/ollama folder we can map it inside our folder and save weights directly in our repo with this commmand. 

```
docker run -it --rm -v "$(pwd)/ollama_files:/root/.ollama" -p 11434:11434 --name ollama ollama/ollama
```

<br>

Now, stop the docker and run our docker file with the saved weights. 

Build and run docker image,

```
docker build -t ollama-gemma2b .
```

```
docker run -it --rm -v "$(pwd)/ollama_files:/root/.ollama" -p 11434:11434 ollama-gemma2b
```

Then, we can try our ollama model with 

```
client = OpenAI(
    base_url='http://localhost:11434/v1/',
    api_key='ollama',
)
```