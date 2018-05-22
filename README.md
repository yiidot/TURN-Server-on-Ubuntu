# TURN-Server-on-Ubuntu
NAT穿透--TURN Server在Ubuntu上的快速部署

## TURNSERVER
`deployment`
`environment`:`Linux(ubuntu)`
### ignore if you already in admin mode
`sudo -i`

### install the dependencies
`apt-get update && apt-get install libssl-dev libevent-dev libhiredis-dev make -y`

### download the resource
`wget -O turn.tar.gz http://turnserver.open-sys.org/downloads/v4.5.0.3/turnserver-4.5.0.3.tar.gz`

### unzip 
tar -zxvf turn.tar.gz  

### install 
```
cd turnserver-*
./configure
make && make install 
```

### run
`sudo turnserver -a -o -v -n  --no-dtls --no-tls -u test:test -r "someRealm"`

## web-client
```
var config = { "iceServers": [
	{
		"urls": 'turn:123.207.188.35:3478',
		"username": 'test',
		"credential": 'test'
	}
}
```
