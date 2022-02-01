# chrome
A headless Chrome running in Docker for Puppeteer

This Dockerfile is a Frankenstein made with some configurations found online.

## Getting the WebSocket url for Puppeteer
> Simple as cake

```bash
docker run --rm -d \
  -p 9222:9222 \
  --name chrome \
  brugnara/chrome:97
  
# replace chrome with the IP
curl -H host: localhost:9222/json/version | jq .webSocketDebuggerUrl
# "ws://localhost/devtools/browser/5667a913-e872-46a3-9b2d-f3bbe8493f83"
```

## need to run this curl into a CI? 
> Hint

```bash
curl -H host: chrome:9222/json/version | jq .webSocketDebuggerUrl
```
