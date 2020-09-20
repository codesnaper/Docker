#Multi Stage build
#We can have a multiple FROM and whenever we are writing multiple from the new stage build start
FROM golang:1.12.4 AS compiler
WORKDIR /helloworld
COPY helloworld.go .
RUN GOOS=linux go build -a -installsuffix cgo -o helloworld .

#New Stage start and it will only have basic execution file and above stage will removed, so when new image from the size will be 17MB and 
#for inefficient image size is 171 MB
FROM alpine:3.9.3
WORKDIR /root
COPY --from=compiler /helloworld/helloworld .
CMD ["./helloworld"]

#To have efficient Image
#1. Put things that are less likely to change in lover layer
#2. Dont have unecessary layer.
#3. Avoid unnecessary file package, etc 