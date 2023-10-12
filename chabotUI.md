### [Chabot UI](https://github.com/mckaywrigley/chatbot-ui) Setup

Run llama-cpp in webserver mode (a compatible OpenAI API)

```
llama-cpp python3 -m llama_cpp.server --model CEPH/LLM-models/TheBloke_Llama-2-7B-Chat-GGUF/llama-2-13b-chat.Q5_K_M.gguf  --n_gpu_layers 40 --host 10.64.10.36
```

then run the docker for Chabot UI
```
docker run -e OPENAI_API_HOST=http://10.64.10.36:8000  -p 3000:3000 ghcr.io/mckaywrigley/chatbot-ui:main
```

Now you can connect to 10.64.10.36 8000 on the browser to start chatting with the model.
