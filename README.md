# Networks-Project4

This is the fifth project for Networks & Distributed Systems course. 

The assignment description is below:
This assignment is intended to familiarize you with the HTTP protocol. HTTP is (arguably) the most important application level protocol on the Internet today: the Web runs on HTTP, and increasingly other applications use HTTP as well (including Bittorrent, streaming video, Facebook and Twitter’s social APIs, etc.).

Your goal in this assignment is to implement a web crawler that gathers data from a fake social networking website that we have set up for you. There are several educational goals of this project:

- To expose you to the HTTP protocol, which underlies a large (and growing) number of applications and services today.
- To let you see how web pages are structured using HTML.
- To give you experience implementing a client for a well-specified network protocol.
- To have you understand how web crawlers work, and how they are used to implement popular web services today.

## High-Level Approach

The protocol is implemented in Python and consists of ___

# Previous example must rewrite
1. **Sliding Window**: The sender maintains a sliding window with a dynamic size, which is updated based on the rate of successful acknowledgements. The window size is increased for successful transmissions and decreased for timeouts.

## Challenges Faced

# Previous example must rewrite
1. **Handling randomly dropped packets**: The protocol is designed to handle situations where packets are dropped during transmission. The sender uses a timeout mechanism to detect dropped packets and resends them when necessary.

## Features

# Previous example must rewrite
1. **Checksum Validation**: The sender and receiver use Adler-32 checksums to detect and discard corrupted packets.

## Testing

The code was tested with