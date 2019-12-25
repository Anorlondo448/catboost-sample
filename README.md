# Bring-your-own Algorithm Sample (CatBoost)

# Usage

## Local test
```
chmod +x catboost/train
chmod +x catboost/serve
```
```
docker build -t catboost-tut .
```

```
docker run --rm -v $(pwd)/local_test/test_dir:/opt/ml catboost-tut train
```

```
docker run --rm -p 127.0.0.1:8080:8080 -v $(pwd)/local_test/test_dir:/opt/ml 
catboost-tut serve
```

## ECR Push(for use SageMaker)
```
docker tag catboost-tut:latest <aws-id>.dkr.ecr.<region>.amazonaws.com/catboost-tut:latest
```

```
docker push <aws-id>.dkr.ecr.<region>.amazonaws.com/catboost-tut:latest
```