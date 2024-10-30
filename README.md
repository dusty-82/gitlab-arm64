# git clone https://github.com/dusty-82/gitlab-arm64
# cd gitlab-arm64
# export RELEASE_VERSION=17.5.1
# docker build . -t gitlab-arm64:$RELEASE_VERSION-ce --build-arg RELEASE_PACKAGE=gitlab-ce --build-arg RELEASE_VERSION=$RELEASE_VERSION-ce
# docker login -u username docker.io
# docker tag gitlab-arm64:$RELEASE_VERSION-ce dusty82/gitlab-arm64:$RELEASE_VERSION-ce
# docker push dusty82/gitlab-arm64:$RELEASE_VERSION-ce

# kubectl apply -f gitlab.yaml
