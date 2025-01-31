# Networking Notes

## OSI Model and Functions

| Layer          | Function                                                                            |
| -------------- | ----------------------------------------------------------------------------------- |
| Application    | end user applications. i.e. HTTP, DNS, FTP                                          |
| Presentation   | Defining data formats and converting data. E.g ASCII, Binary, Encryption, JPEG etc. |
| Session        | app session coordination, setup, maintenance, termination                           |
| Transport      | end to end data transfer. TCP/UDP unicast vs multicast                              |
| Network        | packet forwarding, routing, subnet masking                                          |
| Data Link      | error correct, node to node data transfer (e.g. switches, hubs)                     |
| Physical Layer | cables, ethernet, bandwidth                                                         |

`NOTE`: TCP/IP is the same but Application, presentation, sessions are combined into application.

---

## Physical Layer

#### Responsible for trasnmitting individual bits from one node to another

- Transmission medium between sender and receiver
- can be air or cable
- point to point vs multipoint connection (direct vs branch out to multiple devices)
- bit encoding
- synchronisation of clocks
- cable types (simplex, half-duplex, duplex)

## Data Link Layer

#### Responsible for transmitting frames between network and physical layer

- Framing
- Physical addressing
- flow control
- Error control
- Access control (control collisions)

### DLC (data link control layer)

- Framing (fixed sized vs variable)
- Parity checking

## Network Layer

#### Responsible for source to destination delivery of packets

- logical addressing (e.g. 192.168.1.0)
- routing (between `networks`)

## Transport Layer

- Service point addressing
- segmentation and reassembly
- connection control (connection oriented or connectionless)
- flow control (end to end)
- error control (process to process)

#### Common ports

- 8080 (http), 21 (FTP), 22 (SSH), 53 (DNS)

## Session Layer

#### Responsible for dialog control and synchronisation

## Presentation Layer

#### Responsible for translation, compression and encryption between session and application layers

## Application Layer

#### response for providing services to the end user
