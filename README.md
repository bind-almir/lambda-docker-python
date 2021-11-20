#Build and test on  your local machine
`docker build . -t test/docker-lambda`
`docker run -p 9000:8080 test/docker-lambda:latest`
`curl -XPOST "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{}'`

#Setup GitHub actions
- Clone the repository
- Add `AWS_ACCESS_KEY_ID` and `AWS_ACCESS_KEY_ID` to GitHub secrets
- Push to `master` will deploy to AWS (check `.github/workflows/deploy.yml` for details)