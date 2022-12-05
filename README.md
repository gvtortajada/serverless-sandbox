# serverless-sandbox

## deploy cloud function gen2
```
gcloud functions deploy nodejs-http-function \
  --gen2 \
  --runtime nodejs16 \
  --entry-point helloWorld \
  --source . \
  --region northamerica-northeast1 \
  --trigger-http \
  --timeout 600s
```

## Invoking cloud function
```
export URL=<add Cloud function URL here>
curl -m 610 -X POST $URL \
-H "Authorization: bearer $(gcloud auth print-identity-token)" \
-H "Content-Type: application/json" \
-d '{
  "name": "Hello World"
}'
```