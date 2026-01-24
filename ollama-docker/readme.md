Once you successfully execute

```
docker compose up -d
```

Wait for around 5 minutes, till it finishes pulling the model. You can inspect logs to see progress if you want with command

```
docker logs -f ollama
```

Once both the models have been fetched to verify that set up is working completely you can make http calls 

```
curl http://localhost:11434/api/tags
```

```
curl http://localhost:11434/api/chat -d '{
  "model": "tinyllama",
  "messages": [
    { "role": "user", "content": "why is the sky blue?" }
  ],
  "stream": false
}'
```

Both of them should yield 200 response with second http call responding to the question asked.