# The book of Swarm
storage and communication infrastructure for self-sovereign digital society back-end stack for the decentralised web
Viktor Trón
v1.0 pre-release 7 - worked on November 17, 2020

CONTENTS Prolegomena xi
Acknowledgments xii
## i prelude
###  1 the evolution  > ready for review :wink:

#### 1.1 Historical context

1.1.1 Web 1.0
1.1.2 Web 2.0
1.1.3 Peer-to-peer networks 6
1.1.4 The economics of BitTorrent and its limits
1.1.5 Towards Web 3.0 8

#### 1.2 Fair data economy 12
1.2.1 The current state of the data economy 12
1.2.2 The current state and issues of data sovereignty
1.2.3 Towards self-sovereign data 15
1.2.4 Artificial intelligence and self-sovereign data
1.2.5 Collective information 17

#### 1.3 The vision 18
1.3.1 Values 18
1.3.2 Design principles
1.3.3 Objectives 19
1.3.4 Impact areas
1.3.5 The future 21
ii design and architecture
## 2 network > ongoing @taoshengshi:yum:
#### 2.1 Topology and routing
2.1.1 Requirements for underlay network 25
#### 2.2 Swarm
2.2.1 Distributed immutable store for chunks
2.2.2 Content addressed chunks 38
2.2.3 Single-owner chunks 41
2.2.4 Chunk encryption 42
2.2.5 Redundancy by replication 43
#### 2.3 Push and pull: chunk retrieval and syncing
2.3.1 Retrieval 47
2.3.2 Push syncing 51
2.3.3 Pull syncing 53
2.3.4 Light nodes 55
## 3 incentives
### 3.1 Sharing bandwidth  > ready for review :wink:
3.1.1 Incentives for serving and relaying 58
3.1.2 Pricing protocol for chunk retrieval 59
3.1.3 Incentivising push-syncing 

### 3.2 Swap: accounting and settlement  > ready for review :wink:

3.2.1 Peer to peer accounting
3.2.2 Cheques as off-chain commitments to pay
3.2.3 Waivers 70
3.2.4 Best effort settlement strategy 71
3.2.5 Zero cash entry 73
3.2.6 Cashing out and risk of insolvency
3.2.7 Sanctions and blacklisting 74

#### 3.3 Storage incentives > ongoing @taoshengshi:yum:
3.3.1 Spam protection with postage stamps
3.3.2 Postage lottery: positive incentives for storage
3.3.3 Price signalling capacity pressure
3.3.4 Insurance: negative incentives
#### 3.4 Summary 94
##  4 high-level functionality  
#### 4.1 Data structures 
4.1.1 Files and the Swarm hash 
4.1.2 Collections and manifests 
4.1.3 URL-based addressing and name resolution
4.1.4 Maps and key–value stores 
#### 4.2 Access control 
4.2.1 Encryption 
4.2.2 Managing access 
4.2.3 Selective access to multiple parties 106
4.2.4 Access hierarchy 
#### 4.3 Swarm
4.3.1 Feed chunks 109
4.3.2 Indexing schemes 111
4.3.3 Integrity 114
4.3.4 Epoch-based indexing 115
4.3.5 Real-time data exchange 117
#### 4.4 Pss: direct push messaging with mailboxing 121
4.4.1 Trojan chunks 122
4.4.2 Initial contact for key exchange 125
4.4.3 Addressed envelopes 128
4.4.4 Notification requests 131
## 5 persistence 138
### 5.1 Redundancy, latency and repair 138
5.1.1 Error correcting codes 138
5.1.2 Redundancy by erasure codes 139
5.1.3 Per-level erasure coding in the Swarm chunk tree 139
### 5.2 Pinning, reupload and missing chunk notifications 142
5.2.1 Local pinning 142
5.2.2 Global pinning 143
5.2.3 Recovery 144
### 5.3 Insurance 148
5.3.1 Insurance pool 148
5.3.2 Buying insurance on a chunk
5.3.3 Uploading with insurance
5.3.4 Accessing receipts 148
## 6 user experience 150
### 6.1 Configuring and tracking uploads
6.1.1 Upload options 150
6.1.2 Upload tags and progress bar
6.1.3 Postage 152
6.1.4 Additional upload features
### 6.2 Storage
6.2.1 Uploading files 155
6.2.2 Collections and manifests 156
6.2.3 Access control 157
6.2.4 Download 158
#### 6.3 Communication 160
6.3.1 Feeds 160
6.3.2 Pss 160
### 6.4 Swarm
6.4.1 Primitives 161
6.4.2 Scripting 161
6.4.3 Built-in composite APIs
6.4.4 Standard library 161

# iii specifications
##List of definitions 165
##7 data types and algorithms 168
###7.1 Built-in primitives 168 7.1.1 Crypto 168
7.1.2 State store 174
7.1.3 Local context and configuration 174
### 7.2 Bzz address 175
7.2.1 Overlay address 175
7.2.2 Underlay address 175
7.2.3 BZZ address 176
### 7.3 Chunks, encryption and addressing 177
7.3.1 Content addressed chunks 177
7.3.2 Single owner chunk 179
7.3.3 Binary Merkle Tree Hash 181
7.3.4 Encryption 182
### 7.4 Files, manifests and data structures 184
7.4.1 Files and the Swarm hash 184
7.4.2 Manifests 187
7.4.3 Resolver 191
7.4.4 Pinning 191
7.4.5 Tags 192
7.4.6 Storage 193
### 7.5 Access Control 193
### 7.6 PSS
7.6.1 PSS message 196
7.6.2 Direct pss message with trojan chunk 196
7.6.3 Envelopes 200
7.6.4 Update notifications 200
7.6.5 Chunk recovery 200
### 7.7 Postage stamps 201
7.7.1 Stamps for upload
7.7.2 Postage subscriptions
7.7.3 Postage lottery race
## 8 protocols 204
### 8.1 Introduction 204

8.1.1 Underlay network
8.1.2 Protocols and streams
8.1.3 Data exchange sequences 205
8.1.4 Stream headers 206
8.1.5 Encapsulation of context for tracing 206
### 8.2 Bzz handshake protocol 207
8.3 Hive discovery 208
8.3.1 Streams and messages 208
8.4 Retrieval 209
8.5 Push-syncing 210
8.6 Pull-syncing 210

### 8.7 SWAP settlement protocol 210 

## 9 strategies 211
### 9.1 Connection 211
9.1.1 Connectivity and its constraints 212
9.1.2 Light node connection strategy 212
### 9.2 Forwarding 212
### 9.3 Pricing 213
9.3.1 Passive strategy
9.3.2 Behavior of a node
### 9.4 Accounting and settlement
### 9.5 Push-syncing 216
### 9.6 Pull-syncing 216
### 9.7 Garbage collection 216
## 10 api-s 218
### 10.1 External API requirements
10.1.1 Signer 219
10.1.2 Blockchain 219
10.1.3 User input 220
### 10.2 Storage API 221
10.2.1 Chunks 221
10.2.2 File 223
10.2.3 Manifest 225
10.2.4 High level storage API 227
10.2.5 Tags 230
10.2.6 Pinning 232
10.2.7 Swap and chequebook 233
10.2.8 Postage stamps 233
10.2.9 Access Control 236

### 10.3 Communications 237 10.3.1 PSS 237
10.3.2 Feeds 239 Bibliography 239

# iv appendix
### a formalisations and proofs 245

### a.1 Logarithmic distance and proximity order 245

### a.2 Proximity orders in graph topology 246

### a.3 Constructing kademlia topology 247

###  a.4 Complexity of filling up a postage stamp batch 247

###  a.5 Average hop count for chunk retrieval 249

###  a.6 Distribution of requests 249

###  a.7 Epoch-based feeds 249

# v indexes
### Glossary 255
### Index 266
### List of acronyms and abbreviations 270
