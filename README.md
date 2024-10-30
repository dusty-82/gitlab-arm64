# Fai una copia locale del repo
$ git clone https://github.com/dusty-82/gitlab-arm64

# Entra nella directory
$ cd gitlab-arm64

# Exporta la versione di gitlab che vuoi costruire
$ export RELEASE_VERSION=17.5.1

# Esegui la build dell'immagine
$ docker build . -t gitlab-arm64:$RELEASE_VERSION-ce --build-arg RELEASE_PACKAGE=gitlab-ce --build-arg RELEASE_VERSION=$RELEASE_VERSION-ce

# Loggati al repository DockerHub
$ docker login -u username docker.io

# Cambia tag all'immagine creata
$ docker tag gitlab-arm64:$RELEASE_VERSION-ce dusty82/gitlab-arm64:$RELEASE_VERSION-ce

# Invia l'immagine su DockerHub
$ docker push dusty82/gitlab-arm64:$RELEASE_VERSION-ce

# Modifica la versione dell'imagine nel file manifest e applicalo
$ kubectl apply -f gitlab.yaml
