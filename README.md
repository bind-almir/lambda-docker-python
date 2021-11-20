#Build and test on  your local machine
`docker build . -t test/docker-lambda`
`docker run -p 9000:8080 test/docker-lambda:latest`
`curl -XPOST "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{}'`

#Setup GitHub actions
- Clone the repository
- Push to your own GitHub account
- Add `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` to GitHub secrets
- Create `test/docker-lambda` repository on AWS ECR on your account
- Push to `master` will deploy to AWS (check `.github/workflows/deploy.yml` for details)