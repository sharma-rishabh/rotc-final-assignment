## Converting Orchestration to Kubernetes.

Done by Harsha(@harsha-3123) and Rishabh(@sharma-rishabh)

### To bring the resources up. We can run

```sh
kubectl create -f k8s-resources/resources.yaml
```

```sh
kubectl create -f k8s-resources
```

These should create all the required resources.

### Connect to the app from your local machine.

You'd need to forward the kubernetes port to your local host.

```sh
kubectl -n crud-app port-forward service/backend-api-service 8000:8000
```

Post that you can run these commands to connect to the app.

```
curl -X GET http://localhost:8000/users
```

```
curl -X POST http://localhost:8000/users -d '{"name":"John Doe", "email":"jdoe@example.com"}' -H "Content-Type: application/json"
```

```
curl -X DELETE http://localhost:8000/users/1 -H "Content-Type: application/json"
```

Since we are persisting the data. You should see same details across different deployments.
