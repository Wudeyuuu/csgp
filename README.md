# csgp

#CSGP packet

magic(2B) -> 0xfa15
id(4B)    -> 1, 2, 3, ...
size(4B)  -> size of metadata + content, excluding the id, type, subtype, etc.
type(1B)  ->
            0.  NULL
            1.  Ping Client->Server
            2.  Pong Server->Client
            3.  Connect + Hello Client->Server
            4.  Ack Server->Client
            5.  Reject Server->Client
            6.  Ready Server->Client
            7.  Login Client->Server
            8.  Accept Login Server->Client
            9.  Denny Login Server->Client
            10. Close Client->Server
            11. Close Server->Client
            12. Data Client->Server
            13. Data Server->Client
            14. Response Client->Server (response to a packet)
            15. Response Server->Client (response to a packet)
metadata size(4B) -> metadata block size
metadata(metadata size B) ->
                            metadata: 
                                    name size(4B)
                                    data size(4B)
                                    name(name size B)
                                    data(data size B)
subtype(4B) -> custom for each app
content(size - metadata size) -> payload
close(2B) ->0x15fa


