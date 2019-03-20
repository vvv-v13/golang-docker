#init
go mod init mod

go mod vendor
go build -mod vendor
