# coypu-KGQA
Coypu KG Question Answering module for deployment.

# Requirement

- python >= 3.9

Use your favourite virtual environment management tool and

```
pip install -r requirements.txt
```

# Usage

## Docker
Alternatively, you can deploy via docker, which will be using port 12000. 
```
docker-compose up
```

and query via post request,
```
curl -i -H "Content-Type: application/json" -X POST -d '{"text": "What is the risk level of Germany?", "kb": "coypukg"}' http://127.0.0.1:12000
```
