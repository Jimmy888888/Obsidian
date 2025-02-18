- #[[BTC Core]]
- #[[P2P Protocol]]
- ## Intro
	- Bitcoin's network communication module is the core of its peer-to-peer network, enabling message exchange and data synchronization between nodes. This section introduces the basic concepts, source code structure, and key implementations of Bitcoin's network communication.
-
- ## 1. Basic Concepts of Network Communication
	- ### (1) Node Types
		- Bitcoin's network consists of the following types of nodes:
			- Full Node
			- SPV Node
			- Mining Node
	- ### (2) Message Passing Mechanism
		- Bitcoin uses a peer-to-peer protocol, where each node communicates with others over TCP connections. Common message types include:
			- **`version`**: Sent during node initialization, containing protocol version, timestamp, and other details.
			- **`inv`**: Notifies peers of available block or transaction hashes.
			- **`getdata`**: Requests specific block or transaction data.
			- **`block`**: Sends a complete block.
			- **`tx`**: Sends a specific transaction.
	- ### (3) Network Synchronization
		- Bitcoin propagates transactions and blocks through the network. All nodes work together to maintain the blockchain's consistency and up-to-date state.
-
- ## 2. Source Code Locations for Network Communication
	- The network communication functionality of Bitcoin is primarily implemented in the following files:
		- **`net.cpp` and `net.h`**: Core logic for network connections and message passing.
		- **`protocol.cpp` and `protocol.h`**: Defines the format and protocol for network messages.
		- **`net_processing.cpp` and `net_processing.h`**: Handles incoming network messages.
-
- ## 3. Detailed Analysis of the Network Communication Module
	- ### (1) Network Initialization
		- When Bitcoin starts, the network module initializes and performs the following tasks:
			- **Bind Ports**: Listens for connections from other nodes.
			- **Load Node Configuration**: Loads known nodes from the `peers.dat` file.
			- **Establish Connections**: Actively connects to other nodes.
			  
			  Example code:  
			  ```cpp
			  void StartNode() {
			      // Start listening for connections
			      if (!BindListenPort()) {
			          throw std::runtime_error("Failed to bind to port");
			      }
			      // Initialize connection pool
			      ConnectToPeers();
			  }
			  ```
	- ### (2) Node Connections
		- Bitcoin uses the **`CNode`** class to represent a network connection. Key attributes include:
			- **`addr`**: The IP address of the node.
			- **`fInbound`**: Indicates whether the connection is inbound.
			- **`nVersion`**: Records the protocol version used by the node.
			  
			  Each node connects to multiple peers, forming a distributed network.
	- ### (3) Message Processing
		- Bitcoin messages follow a fixed format:
			- **Message Header**: Contains the message type, length, and checksum.
			- **Message Body**: Contains the actual data.
			  
			  Key steps for processing messages:
				- Parse the message type from the header when receiving data.
				- Call the corresponding message handler, e.g., for `tx` or `block` messages.
				- Validate the content (e.g., check block hashes).
				- Broadcast the message or request additional data if necessary.
				  
				  Example code:  
				  ```cpp
				  bool ProcessMessage(CNode* pfrom, const std::string& strCommand, CDataStream& vRecv) {
				    if (strCommand == "version") {
				        // Handle version information
				        return HandleVersionMessage(pfrom, vRecv);
				    } else if (strCommand == "tx") {
				        // Handle transaction data
				        return HandleTxMessage(pfrom, vRecv);
				    } else if (strCommand == "block") {
				        // Handle block data
				        return HandleBlockMessage(pfrom, vRecv);
				    }
				    return false;
				  }
				  ```
	- ### (4) Network Synchronization
		- Bitcoin nodes synchronize the blockchain using the following steps:
			- **Node Handshake**
				- Newly connected nodes exchange `version` and `verack` messages to confirm protocol version and capabilities.
			- **Fetch Blockchain State**
				- Nodes send `getheaders` requests to retrieve block header information from peers.
			- **Sync Blocks**
				- If differences are detected, nodes send `getdata` requests to retrieve missing blocks.
-
- ## 4. Experiment: Implementing Custom Message Sending
	- Below is a simple example of how to implement custom message sending and handling:
	- ### (1) Define Custom Message
		- Add a new message type in `protocol.h`:  
		  ```cpp
		  const char* const MSG_MYCOMMAND = "mycommand";
		  ```
	- ### (2) Send Message
		- Call the following code to send a custom message:  
		  ```cpp
		  CDataStream ssSend(SER_NETWORK, PROTOCOL_VERSION);
		  ssSend << "Hello, Bitcoin!";
		  pnode->PushMessage(MSG_MYCOMMAND, ssSend);
		  ```
	- ### (3) Process Message
		- Add the handling logic in `ProcessMessage`:  
		  ```cpp
		  if (strCommand == MSG_MYCOMMAND) {
		      std::string message;
		      vRecv >> message;
		      LogPrintf("Received custom message: %s\n", message);
		  }
		  ```
-
- ## 5. Advanced Topics and Optimization
- ### (1) Network Security
	- The Bitcoin network must defend against the following attacks:
		- **Denial of Service (DoS)**: Overloading nodes with spam messages.
		- **Man-in-the-Middle Attack**: Intercepting and altering transactions.
- ### (2) Data Propagation Optimization
	- Bitcoin employs the following techniques to optimize message propagation:
		- **[[Mempool]]**: Nodes cache unconfirmed transactions to avoid duplicate requests.
		- **Bloom Filter**: Lightweight nodes use bloom filters to receive only relevant transactions.
-
- Through this tutorial, you can gain a deep understanding of the design and implementation of Bitcoin's network communication module. For further study, refer to the comments in `net.cpp` and `protocol.cpp`, and experiment with modifying the code.