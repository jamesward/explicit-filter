# Explicit Filter

[![Run on Google Cloud](https://deploy.cloud.run/button.png)](https://deploy.cloud.run)

## Local Dev

Run the server:
```
./gradlew bootRun
```

Test it:
```
curl localhost:8080/filter \
  -H "ce-id: 0001"  \
  -H "ce-specversion: 1.0" \
  -H "ce-type: filter" \
  -H "ce-source: spring.io/spring-event" \
  -H "Content-Type:" \
  -d 'asdf foo zxcv'
```

Create JVM container
```
./gradlew bootBuildImage --imageName=explicit-filter
```

Create native container
```
./gradlew bootBuildImageNative --imageName=explicit-filter
```

run with docker:
```
docker run -it -p8080:8080 explicit-filter
```
