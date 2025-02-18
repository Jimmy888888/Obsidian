- #[[BTC Core]]
- #### Goal:
	- Monitor the Bitcoin mempool in real-time to detect transactions paying to specific addresses.
- #### Steps:
	- **Subscribe to `rawtx` events**:
		- This allows your application to receive raw transaction data from the node.
	- **Parse the transaction data**:
		- Decode the raw transaction to extract inputs, outputs, and associated addresses.
	- **Match specific addresses**:
		- Check if any output in the transaction matches the payment address(es) you're monitoring.
	- #### Example Code:
	  
	  ```
	  #python
	  import zmq
	  from bitcoin.rpc import RawProxy  # Install python-bitcoinlib for this
	  
	  # ZMQ Setup
	  context = zmq.Context()
	  socket = context.socket(zmq.SUB)
	  socket.connect("tcp://127.0.0.1:28333")  # Adjust the ZMQ endpoint
	  socket.setsockopt_string(zmq.SUBSCRIBE, "rawtx")
	  
	  # Bitcoin Core RPC setup
	  rpc = RawProxy()
	  
	  print("Monitoring transactions for payments...")
	  while True:
	    topic, raw_tx = socket.recv_multipart()
	    print(f"Received transaction: {raw_tx.hex()}")
	  
	    # Decode the raw transaction
	    tx_details = rpc.decoderawtransaction(raw_tx.hex())
	    for output in tx_details["vout"]:
	        # Check if any output address matches
	        if "addresses" in output["scriptPubKey"]:
	            for address in output["scriptPubKey"]["addresses"]:
	                if address == "your_payment_address_here":
	                    print(f"Payment detected to {address}")
	  ```
	  
	  ---