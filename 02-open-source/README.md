### Ollama with Docker 

```
docker run -it -v ollma:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

`docker exec -it ollama bash`

`ollama -v`

`ollama version is 0.1.48`

metadata file inside `models/manifests/registry.ollama.ai/library` - `gemma/2b`

Test Prompt - `10*10`

Answer -

``` 
Sure. The given code is:

```python
10 * 10
```

Insted of mapping ./root/ollama folder we can map it inside our folder. 

```
docker run -it -v ollma:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

```
docker run -it --rm -v "$(pwd)/ollama_files:/root/.ollama" -p 11434:11434 --name ollama ollama/ollama
```

Now, stop the docker and run our docker file. 

Build and run docker image,

```
docker build -t ollama-gemma2b .
```

```
docker run -it --rm -v "$(pwd)/ollama_files:/root/.ollama" -p 11434:11434 ollama-gemma2b
```


Result of running ollama_test.py


ChatCompletion(id='chatcmpl-263', choices=[Choice(finish_reason='stop', index=0, logprobs=None, message=ChatCompletionMessage(content="Sure, here's the formula for energy:\n\n**E = K + U**\n\nWhere:\n\n* **E** is the energy in joules (J)\n* **K** is the kinetic energy in joules (J)\n* **U** is the potential energy in joules (J)\n\n**Kinetic energy (K)** is the energy an object possesses when it moves or is in motion. It is calculated as half the product of an object's mass (m) and its velocity (v) squared:\n\n**K = 1/2mv^2**\n\n**Potential energy (U)** is the energy an object possesses due to its position or configuration. It is calculated as the product of an object's mass, gravitational constant (g), and height or position above a reference point.\n\n**U = mgh**\n\nWhere:\n\n* **m** is the mass in kilograms (kg)\n* **g** is the gravitational constant (9.8 m/s^2)\n* **h** is the height or position in meters (m)\n\nThe formula shows that energy can be expressed as the sum of kinetic and potential energy. The kinetic energy is a measure of the object's ability to do work, while the potential energy is a measure of the object's ability to do work against a force.", role='assistant', function_call=None, tool_calls=None))], created=1720383761, model='gemma:2b', object='chat.completion', service_tier=None, system_fingerprint='fp_ollama', usage=CompletionUsage(completion_tokens=281, prompt_tokens=34, total_tokens=315))

