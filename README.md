# p2p-poc

## Introduction
This is a POC, about implementing the `libp2p`'s `go-libp2p` package for implementing a basic peer-to-peer publisher/subscriber (pubsub) system with using the `go-libp2p-pubsub` package. Using the `gossipsub` peer-to-peer pubsub implementations.

### libp2p
[libp2p](https://docs.libp2p.io/) is a network framework that allows you to write decentralized peer-to-peer applications. It evolved out of `IPFS` and became an independent project. There are certainly a ton of applications being built using `libp2p`. `IPFS`, `Parity`, `Ethereum`, `Filecoin`, `Polkadot` are some popular examples. `libp2p` provides flexible solutions for essential peer-to-peer elements like *transport*, *security*, *peer-routing*, and *content-discovery*. It consists of a catalogue of modules from which p2p network developers can select and reuse just the protocols they need, while making it easy to upgrade and interoperate between applications. libp2p has implementations in [`Go`](https://github.com/libp2p/go-libp2p), [`JavaScript`](https://github.com/libp2p/js-libp2p), [`Rust`](https://github.com/libp2p/rust-libp2p), [`Python`](https://github.com/libp2p/py-libp2p), and [`C++`](https://github.com/libp2p/cpp-libp2p). The specification of libp2p can be found in its [specs repo](https://github.com/libp2p/specs).

### gossipsub
The libp2p-pubsub has created a number of peer-to-peer pubsub implementations(e.g gossipsub, floodsub, fpisub) that have enabled real time peer-to-peer pubsub application development(read more about these different pubsub implementation from [here](https://hackernoon.com/exploring-libp2p-pubsub-protocol-implementations-891i32jq)). `gossipsub` is named after the fact that peers gossip to each other about which messages they have seen and use this information to maintain a message delivery network.

## Scenario
In this post I have discussed about developing simple pubsub application with libp2p gossipsub. In the pubsub application, the publisher peer take messages from command line and push them to a topic called *p2p-pubsub*. Then the subscribers of that *p2p-pubsub* topic receive the data via peer-to-peer gossipsub. This is a simplified version of my pubsub system.

## Run the Pub-Sub

Follow the below steps to run your local pubsub system:
> Step 1: Clone the repository by running this command: `git clone https://github.com/amancooks08/p2p-poc.git`.
> Step 2: Enter the directory by running the command `cd p2p-poc`.
> Step 3: Run the `go mod tidy` to make sure you have all the dependencies installed.
> Step 4: Open a Terminal and start your subscriber, by running the command: ` go run subscriber/subscriber.go`.
> Step 5: Open another terminal and start your publisher, by running the command: `go run publisher/publisher.go`.
> Step 6: Send a message and check in the subscriber terminal to see that it has been received.