# Project-Diana-Docker

Build container using
`docker build -t <image-name>:<tag> .`

Build with multiple architectures (ex. x86 and arm)
`docker buildx build --platform linux/amd64,linux/arm64 -t <image-name>:<tag> -f Dockerfile --push .`

Run container using
`docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=<password>' --name '<container-name>' -e 'MSSQL_PID=Express' -p 1433:1433 -d <image-name>:<tag>`
