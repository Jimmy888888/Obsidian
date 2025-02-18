- #[[BTC Core]]
- #### Goal:
	- Create a real-time blockchain explorer that displays newly mined blocks and transactions as they occur.
- #### Steps:
	- **Subscribe to `rawblock` and `rawtx` events**.
	- **Decode blocks and transactions** using libraries like `python-bitcoinlib`.
	- **Store and display data** in a database or frontend.
	- #### Example Code:
	  
	  ```
	  #python
	  
	  import zmq
	  import json
	  from bitcoin.rpc import RawProxy
	  
	  # ZMQ Setup
	  context = zmq.Context()
	  socket = context.socket(zmq.SUB)
	  socket.connect("tcp://127.0.0.1:28332")  # For rawblock
	  socket.setsockopt_string(zmq.SUBSCRIBE, "rawblock")
	  
	  # Bitcoin Core RPC setup
	  rpc = RawProxy()
	  
	  print("Real-time block monitoring...")
	  while True:
	    topic, raw_block = socket.recv_multipart()
	    print(f"New block received!")
	  
	    # Decode raw block
	    block_hash = rpc.getblockhash(raw_block.hex())
	    block_details = rpc.getblock(block_hash)
	  
	    print(json.dumps(block_details, indent=2))
	  ```
	  
	  ---