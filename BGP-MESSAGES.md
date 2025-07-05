## BGP MESSAGES
 - Variable length from 19 to 4096 bytes 
```
	+-------------------------------+-------------+
	|          Content              |   Header    |
	+-------------------------------+-------------+
		         BGP MESSAGE						
	!<------------------------------------------->!
```
# Header 

- All messages have a common header, whose format is below 

```
	0                   1                   2                   3
	0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
	+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
	|                                                               |
	+                                                               +
	|                                                               |
	+                                                               +
	|                           Marker                              |
	+                                                               +
	|                                                               |
	+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
	|          Length               |      Type     |
	+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

* Marker:
  - 16 bytes
  - Indicates whether the information synchronized between BGP peers is complete.
  - This field is used for calculation in BGP validation. If no validation is used, the field is set to all #1s
    
* Length:
  - 2 bytes
  - It refers to the message’s total length, including the header.
 
* Type:
  - 1 byte
  - 1 = OPEN
  - 2 = UPDATE
  - 3 = NOTIFICATION
  - 4 = KEEPALIVE
  - 5 = ROUTE REFRESH 
