
# How to Install in Linux/Mac

```
You may install go_ibm_db using either of below commands
go get -d github.com/ibmdb/go_ibm_db
go install github.com/ibmdb/go_ibm_db/installer@latest
go install github.com/ibmdb/go_ibm_db/installer@0.4.1


If you already have a cli driver available in your system, set the below environment variables with the clidriver path

export DB2HOME=/home/uname/dsdriver
export CGO_CFLAGS=-I$DB2HOME/include
export CGO_LDFLAGS=-L$DB2HOME/lib 
Linux:
export LD_LIBRARY_PATH=/home/uname/dsdriver/lib
or
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$DB2HOME/lib
Mac:
export DYLD_LIBRARY_PATH=$DYLD_LIBRARY_PATH:/Applications/dsdriver/lib

If you do not have a clidriver available in your system, use below command:
go to installer folder where go_ibm_db is downloaded in your system 
(Example: /home/uname/go/src/github.com/ibmdb/go_ibm_db/installer or /home/uname/go/pkg/mod/github.com/ibmdb/go_ibm_db/installer 
where uname is the username) and run setup.go file (go run setup.go)

Set the below envronment variables with the path of the clidriver downloaded

export DB2HOME=/home/uname/go/src/github.com/ibmdb/clidriver
export CGO_CFLAGS=-I$DB2HOME/include
export CGO_LDFLAGS=-L$DB2HOME/lib
Linux:
export LD_LIBRARY_PATH=/home/uname/go/src/github.com/ibmdb/clidriver/lib
or
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$DB2HOME/lib
Mac:
export DYLD_LIBRARY_PATH=$DYLD_LIBRARY_PATH:/home/uname/go/src/github.com/ibmdb/clidriver/lib
or
export DYLD_LIBRARY_PATH=$DYLD_LIBRARY_PATH:$DB2HOME/lib


Script file to set environment variables in Linux/Mac 
cd .../go_ibm_db/installer
source setenv.sh

For Docker Linux Container, use below commands
yum install -y gcc git go wget tar xz make gcc-c++
cd /root
curl -OL https://golang.org/dl/go1.17.X.linux-amd64.tar.gz
tar -C /usr/local -xzf go1.17.X.linux-amd64.tar.gz

rm /usr/bin/go
rm /usr/bin/gofmt
cp /usr/local/go/bin/go /usr/bin/
cp /usr/local/go/bin/gofmt /usr/bin/

go install github.com/ibmdb/go_ibm_db/installer@v0.4.1
or 
go install github.com/ibmdb/go_ibm_db/installer@latest

```

# Hosting

[Hosting](https://public.dhe.ibm.com/ibmdl/export/pub/software/data/db2/drivers/odbc_cli/)


