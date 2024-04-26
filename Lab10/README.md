*I pledge my Honor that I have abided by Stevens Honor System*

- Study the GitHub repository Lesson 10
- Run hash_value.py twice and compare results
- Run snakecoin.py
- Run snakecoin-server-full-code.py on Terminal 1 and mine a new block on Terminal 2
- Clone Python blockchain app and uncomment the last line of node_server.py
- Run node_server.py on Terminal 1 and run_app.py on Terminal 2

### Lab 10A: Blockchain
Hash function with randomization
Run hash_value.py twice and compare results
```
$ cd ~/iot/lesson10
$ cat hash_value.py

"""
https://docs.python.org/3/using/cmdline.html#envvar-PYTHONHASHSEED
If PYTHONHASHSEED is not set or set to random, a random value is used to to seed the hashes of str and bytes objects.
If PYTHONHASHSEED is set to an integer value, it is used as a fixed seed for generating the hash() of the types covered by the hash randomization.
Its purpose is to allow repeatable hashing, such as for selftests for the interpreter itself, or to allow a cluster of python processes to share hash values.
The integer must be a decimal number in the range [0,4294967295]. Specifying the value 0 will disable hash randomization.

https://www.programiz.com/python-programming/methods/built-in/hash
hash(object) returns the hash value of the object (if it has one). Hash values are integers.
They are used to quickly compare dictionary keys during a dictionary lookup.
Numeric values that compare equal have the same hash value even if they are of different types, as is the case for 1 and 1.0.
For objects with custom __hash__() methods, note that hash() truncates the return value based on the bit width of the host machine.
"""

# hash for integer unchanged
print('The hash for 1 is:', hash(1))

# hash for decimal
print('The hash for 1.0 is:',hash(1.0))
print('The hash for 3.14 is:',hash(3.14))

# hash for string
print('The hash for Python is:', hash('Python'))

# hash for a tuple of vowels
vowels = ('a', 'e', 'i', 'o', 'u')
print('The hash for a tuple of vowels is:', hash(vowels))

# hash for a custom object
class Person:
    def __init__(self, age, name):
        self.age = age
        self.name = name
    def __eq__(self, other):
        return self.age == other.age and self.name == other.name
    def __hash__(self):
        return hash((self.age, self.name))
person = Person(23, 'Adam')
print('The hash for an object of person is:', hash(person))

$ python3 hash_value.py

The hash for 1 is: 1
The hash for 1.0 is: 1
The hash for 3.14 is: 322818021289917443
The hash for Python is: -5203621997928093279
The hash for a tuple of vowels is: -3695261905194000048
The hash for an object of person is: 5570669488893513864

$ python3 hash_value.py

The hash for 1 is: 1
The hash for 1.0 is: 1
The hash for 3.14 is: 322818021289917443
The hash for Python is: -6564652240460053946
The hash for a tuple of vowels is: 4267524046866162921
The hash for an object of person is: -481503347336664824

```
![hash_value](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/e8ecc514-60e6-423f-a74a-24a542f5b41b)

SHA-256 hash values or digests are 256 bits or 32 bytes
Each hexadecimal digit represents four binary digits, a nibble, which is half a byte

```
$ python3
>>> import hashlib
>>> m = hashlib.sha256(b"hello, world")
>>> m.hexdigest()

'4ae7c3b6ac0beff671efa8cf57386151c06e58ca53a78d83f36107316cec125f'

>>> m.digest_size

32

>>> m.block_size

64

>>> exit()
```
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/7b868b48-3d67-40d7-be46-bb031930641e)

Build the tiniest blockchain in less than 50 lines of Python by Gerald Nash (2017-07-16)

```
$ cd ~/iot/lesson10
$ cat snakecoin.py

# Gerald Nash, "Let's build the tiniest blockchain in less than 50 lines of Python"
import hashlib as hasher
import datetime as date

# Define what a Snakecoin block is
class Block:
  def __init__(self, index, timestamp, data, previous_hash):
    self.index = index
    self.timestamp = timestamp
    self.data = data
    self.previous_hash = previous_hash
    self.hash = self.hash_block()

  def hash_block(self):
    sha = hasher.sha256()
    sha.update(str(self.index).encode() + str(self.timestamp).encode() + str(self.data).encode() + str(self.previous_hash).encode())
    return sha.hexdigest()

# Generate genesis block
def create_genesis_block():
  # Manually construct a block with
  # index zero and arbitrary previous hash
  return Block(0, date.datetime.now(), "Genesis Block", "0")

# Generate all later blocks in the blockchain
def next_block(last_block):
  this_index = last_block.index + 1
  this_timestamp = date.datetime.now()
  this_data = "Hey! I'm block " + str(this_index)
  this_hash = last_block.hash
  return Block(this_index, this_timestamp, this_data, this_hash)

# Create the blockchain and add the genesis block
blockchain = [create_genesis_block()]
previous_block = blockchain[0]

# How many blocks should we add to the chain
# after the genesis block
num_of_blocks_to_add = 20

# Add blocks to the chain
for i in range(0, num_of_blocks_to_add):
  block_to_add = next_block(previous_block)
  blockchain.append(block_to_add)
  previous_block = block_to_add
  # Tell everyone about it!
  print("Block #{} has been added to the blockchain!".format(block_to_add.index))
  print("Hash: {}\n".format(block_to_add.hash))

$ python3 snakecoin.py

Block #1 has been added to the blockchain!
Hash: 8e36263e0eeeb14f019ef7b699151c213cbaf11ac9173eb1c50032f11c1961dd

Block #2 has been added to the blockchain!
Hash: eac55414ce6b846ecccf79c99db8e08f558252ee39dab82b9db29d5da986553f

Block #3 has been added to the blockchain!
Hash: 1fd6fc0c613555a7d98797cbfc817b9996b28f9ba4ecc719369d9716b9255489

Block #4 has been added to the blockchain!
Hash: 7f1ae3c3e7fb3754154b40de351f5669d4843a145443821cba30105c096b230e

Block #5 has been added to the blockchain!
Hash: 6dc10f3dfbd1a174b20ac64a890fad5dc8b8757b5b4028163edd6f2597380a3d

Block #6 has been added to the blockchain!
Hash: e10f585da3a4229c45593d19a3e6da2bb7ae643423a630730382f45f8f2cec00

Block #7 has been added to the blockchain!
Hash: 9dcf37a860b4585841e2a942e56cf0331fef7634a535bf8301966b06dc037eb9

Block #8 has been added to the blockchain!
Hash: b69056e6bbdb26bc781cef279f1a12b747e4ecf23b9c146eb8900a0b784bd112

Block #9 has been added to the blockchain!
Hash: ed824492459f32c7d1b4f4b64545f5a6b2d61838ad817f7bdc8fa92539da4fe3

Block #10 has been added to the blockchain!
Hash: e7cb069fb13a45c5b6cc88a369718cc49b1727bd1900cc2e929368a17b11c279

Block #11 has been added to the blockchain!
Hash: 643d7f8463d9840968f32e40729f8e41c447d4a8c94329d4467ae0fab34d9e96

Block #12 has been added to the blockchain!
Hash: 772db68bddb2dc1739be6f6bfdc375e2e777a0075b66c32f8bcf8c62eb7edb00

Block #13 has been added to the blockchain!
Hash: 7024e92afd73042a07839fbfd8d77b5dcfd43a43f2b6220a6a164d4e62b298d0

Block #14 has been added to the blockchain!
Hash: f1db2b6f476397a1ab34fd6d43875c05e8295df2a1ca97c0083e5f51f9cba3f2

Block #15 has been added to the blockchain!
Hash: 5de854d850eb4b490d9f5c76ca4aa0764c2a1633f56aa73fdbd8e150dd47add1

Block #16 has been added to the blockchain!
Hash: d7eccde7b7fcf0de8dabd41aeead3c1ffdb738c6431b5e650774d8fd7b56c6d3

Block #17 has been added to the blockchain!
Hash: f739b6ac88b92800a7d0e237f8a82b2fb1ebcce54ff30c5e42981362985a41d9

Block #18 has been added to the blockchain!
Hash: a781694221a5281c20dc80212c67b5ea4ce6ac20f16fde4aae9df2e361cc604c

Block #19 has been added to the blockchain!
Hash: 624ccb0a843a995c22fe6fa4931d870ca639083034979e2f397d21f467af1b57

Block #20 has been added to the blockchain!
Hash: 411560e9a13cad2daf70baa9b9c56847a903e4f907250c0d716034485e87361f

```

![blockchain](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/f846ca68-8b0c-4979-b339-2492d1cd6c9f)

Let’s Make the Tiniest Blockchain Bigger Part 2: With More Lines of Python by Gerald Nash (2017-07-23)

```
$ cat snakecoin-server-full-code.py

# Gerald Nash, "Let’s Make the Tiniest Blockchain Bigger Part 2: With More Lines of Python"
# Referred to https://www.pythonanywhere.com/forums/topic/12382/ that fixed sha.update() TypeError: Unicode-objects must be encoded before hashing
# Running on http://127.0.0.1:5000/mine (Reload the page to mine and press CTRL+C to quit)
from flask import Flask
from flask import request
import json
import requests
import hashlib as hasher
import datetime as date
from flask import send_from_directory
import os
node = Flask(__name__)

# Define what a Snakecoin block is
class Block:
  def __init__(self, index, timestamp, data, previous_hash):
    self.index = index
    self.timestamp = timestamp
    self.data = data
    self.previous_hash = previous_hash
    self.hash = self.hash_block()

  def hash_block(self):
    sha = hasher.sha256()
#    sha.update(str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash))
    sha.update((str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash)).encode("utf-8"))
    return sha.hexdigest()

# Generate genesis block
def create_genesis_block():
  # Manually construct a block with
  # index zero and arbitrary previous hash
  return Block(0, date.datetime.now(), {
    "proof-of-work": 9,
    "transactions": None
  }, "0")

# A completely random address of the owner of this node
miner_address = "q3nf394hjg-random-miner-address-34nf3i4nflkn3oi"
# This node's blockchain copy
blockchain = []
blockchain.append(create_genesis_block())
# Store the transactions that
# this node has in a list
this_nodes_transactions = []
# Store the url data of every
# other node in the network
# so that we can communicate
# with them
peer_nodes = []
# A variable to deciding if we're mining or not
mining = True

@node.route("/")
def hello():
    return "SnakeCoin Server"

@node.route('/favicon.ico')
def favicon():
    return send_from_directory(os.path.join(node.root_path, 'static'),
                               'favicon.ico',
                               mimetype='image/vnd.microsoft.icon')

@node.route('/txion', methods=['POST'])
def transaction():
  # On each new POST request,
  # we extract the transaction data
  new_txion = request.get_json()
  # Then we add the transaction to our list
  this_nodes_transactions.append(new_txion)
  # Because the transaction was successfully
  # submitted, we log it to our console
  print("New transaction")
  print(("FROM: {}".format(new_txion['from'].encode('ascii','replace'))))
  print(("TO: {}".format(new_txion['to'].encode('ascii','replace'))))
  print(("AMOUNT: {}\n".format(new_txion['amount'])))
  # Then we let the client know it worked out
  return "Transaction submission successful\n"

@node.route('/blocks', methods=['GET'])
def get_blocks():
  chain_to_send = blockchain
  # Convert our blocks into dictionaries
  # so we can send them as json objects later
  for i in range(len(chain_to_send)):
    block = chain_to_send[i]
    block_index = str(block.index)
    block_timestamp = str(block.timestamp)
    block_data = str(block.data)
    block_hash = block.hash
    chain_to_send[i] = {
      "index": block_index,
      "timestamp": block_timestamp,
      "data": block_data,
      "hash": block_hash
    }
  chain_to_send = json.dumps(chain_to_send)
  return chain_to_send

def find_new_chains():
  # Get the blockchains of every
  # other node
  other_chains = []
  for node_url in peer_nodes:
    # Get their chains using a GET request
    block = requests.get(node_url + "/blocks").content
    # Convert the JSON object to a Python dictionary
    block = json.loads(block)
    # Add it to our list
    other_chains.append(block)
  return other_chains

def consensus():
  # Get the blocks from other nodes
  other_chains = find_new_chains()
  # If our chain isn't longest,
  # then we store the longest chain
  longest_chain = blockchain
  for chain in other_chains:
    if len(longest_chain) < len(chain):
      longest_chain = chain
  # If the longest chain isn't ours,
  # then we stop mining and set
  # our chain to the longest one
  blockchain = longest_chain

def proof_of_work(last_proof):
  # Create a variable that we will use to find
  # our next proof of work
  incrementor = last_proof + 1
  # Keep incrementing the incrementor until
  # it's equal to a number divisible by 9
  # and the proof of work of the previous
  # block in the chain
  while not (incrementor % 9 == 0 and incrementor % last_proof == 0):
    incrementor += 1
  # Once that number is found,
  # we can return it as a proof
  # of our work
  return incrementor

@node.route('/mine', methods = ['GET'])
def mine():
  # Get the last proof of work
  last_block = blockchain[len(blockchain) - 1]
  last_proof = last_block.data['proof-of-work']
  # Find the proof of work for
  # the current block being mined
  # Note: The program will hang here until a new
  #       proof of work is found
  proof = proof_of_work(last_proof)
  # Once we find a valid proof of work,
  # we know we can mine a block so
  # we reward the miner by adding a transaction
  this_nodes_transactions.append(
    { "from": "network", "to": miner_address, "amount": 1 }
  )
  # Now we can gather the data needed
  # to create the new block
  new_block_data = {
    "proof-of-work": proof,
    "transactions": list(this_nodes_transactions)
  }
  new_block_index = last_block.index + 1
  new_block_timestamp = this_timestamp = date.datetime.now()
  last_block_hash = last_block.hash
  # Empty transaction list
  this_nodes_transactions[:] = []
  # Now create the
  # new block!
  mined_block = Block(
    new_block_index,
    new_block_timestamp,
    new_block_data,
    last_block_hash
  )
  blockchain.append(mined_block)
  # Let the client know we mined a block
  return json.dumps({
      "index": new_block_index,
      "timestamp": str(new_block_timestamp),
      "data": new_block_data,
      "hash": last_block_hash
  }) + "\n"

node.run()

$ python3 snakecoin-server-full-code.py
$ cd

```

