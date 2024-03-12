git clone

cd gitlab-arm64

RELEASE_VERSION=16.9.1

docker build . -t gitlab-ce:$RELEASE_VERSION-ce --build-arg RELEASE_PACKAGE=gitlab-ce --build-arg RELEASE_VERSION=$RELEASE_VERSION-ce

docker login -u username docker.io

docker tag gitlab-ce:16.9.1-ce usename/gitlab-arm64:16.9.1-ce

kubectl apply -f gitlab.yaml
