---
title: "Creating Your Own Blockchain Using JavaScript and Session/Local Storage"
datePublished: Thu Jun 08 2023 00:22:59 GMT+0000 (Coordinated Universal Time)
cuid: climeabbg000e08laglahf7re
slug: creating-your-own-blockchain-using-javascript-and-sessionlocal-storage
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686183684686/3c15a382-3cc2-4a34-b21c-6e50c6a714a7.jpeg
tags: tutorial, javascript, beginners, blockchain, web3

---

Blockchain is a popular technology that's best known for its implementation in cryptocurrencies such as Bitcoin.

A blockchain is essentially a chain of blocks, where each block holds a collection of data. These blocks are linked together using a cryptographic hash, which is generated from the data within the block.

Despite the intricate nature of real-world blockchains, you can create a simple blockchain of your own with basic coding knowledge.

In this tutorial, we'll use JavaScript to build a rudimentary blockchain and store it in the browser's LocalStorage.

## Step 1: Create a Block Class

First, let's define a `Block` class. Each block will contain an index, timestamp, data, previous hash, and its own hash.

```javascript
class Block {
    constructor(index, timestamp, data, previousHash = '') {
        this.index = index;
        this.timestamp = timestamp;
        this.data = data;
        this.previousHash = previousHash;
        this.hash = this.calculateHash();
    }

    async calculateHash() {
        const msgUint8 = new TextEncoder().encode(this.index + this.previousHash + this.timestamp + JSON.stringify(this.data));                                  
        const hashBuffer = await crypto.subtle.digest('SHA-256', msgUint8);                    
        const hashArray = Array.from(new Uint8Array(hashBuffer));                    
        const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join(''); 
        return hashHex;
    }
}
```

Here, `calculateHash` is a method that returns a SHA-256 hash created from the block's contents.

## Step 2: Create a Blockchain Class

Next, we'll define a `Blockchain` class. This class will maintain a chain of blocks and provide methods to add new blocks and validate the chain.

```javascript
class Blockchain {
    constructor() {
        this.chain = [ this.createGenesisBlock() ];
    }

    createGenesisBlock() {
        return new Block(0, ( new Date() ).toString(), "Genesis Block", "0");
    }

    getLatestBlock() {
        return this.chain[ this.chain.length - 1 ];
    }

    addBlock(newBlock) {
        newBlock.previousHash = this.getLatestBlock().hash;
        newBlock.hash = newBlock.calculateHash();

        this.chain.push( newBlock );
    }

    isChainValid() {
        for( let i = 1; i < this.chain.length; i++ ) {
            const currentBlock = this.chain[ i ];
            const previousBlock = this.chain[ i - 1 ];

            if( currentBlock.hash !== currentBlock.calculateHash() ) {
                return false;
            }

            if( currentBlock.previousHash !== previousBlock.hash ) {
                return false;
            }
        }
        return true;
    }
}
```

`createGenesisBlock` is a method that creates the first block in the chain, also known as the Genesis Block.

`getLatestBlock` returns the last block in the chain, and `addBlock` adds a new block to the chain.

The `isChainValid` method is used to validate the integrity of the blockchain by looping through all blocks and comparing hashes.

## Step 3: Using the Blockchain

Let's test our blockchain:

```javascript
let myBlockchain = new Blockchain();

myBlockchain.addBlock(
    new Block( 
        1, 
        (new Date()).toString(), 
        { amount: 4 }    
    )
);

myBlockchain.addBlock(
    new Block(
        2, 
        (new Date()).toString(), 
        { amount: 8 }
    )
);
```

We created a new Blockchain instance and added two new blocks to it. Each block has an index, a timestamp, and some data. The data can be anything you want; in this case, it's an object with an `amount` property.

## Step 4: Storing the Blockchain in LocalStorage

Now that we've created our blockchain, we can store it in LocalStorage:

```javascript
localStorage.setItem( 'blockchain', JSON.stringify( myBlockchain ) );
```

And if you want to retrieve your blockchain from LocalStorage:

```javascript
let blockchainFromStorage = JSON.parse( localStorage.getItem( 'blockchain' ) );
```

## Conclusion

In this guide, we've covered the basics of creating a simple blockchain using JavaScript and storing it in the browser's LocalStorage.

Remember, this is a very basic implementation of a blockchain, and real-world blockchains are significantly more complex, often involving proof-of-work systems, distributed networks, and other advanced features.

Keep in mind that LocalStorage is not permanent, and it's limited in size (usually around 5MB).

This makes it unsuitable for a real blockchain, which can take up gigabytes or even terabytes of data.

However, it's a handy way to learn about the fundamental concepts behind blockchains. Happy coding!