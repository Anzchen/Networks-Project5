Networks-Project4
This is the fourth project for Networks & Distributed Systems course.

The assignment description is below: You will design a simple transport protocol that provides reliable datagram service. Your protocol will be responsible for ensuring data is delivered in order, without duplicates, missing data, or errors. Since the local area networks at Northeastern are far too reliable to be interesting, we will provide you with access to a virtual machine that will emulate an unreliable network.

For the assignment, you will write code that will transfer a file reliably between two nodes (a sender and a receiver). You may assume that the receiver is run first and will wait indefinitely, and the sender can just send the data to the receiver.

High-Level Approach
The protocol is implemented in Python and consists of two components: the Sender and the Receiver. The sender reads data from standard input and sends it to the receiver, who outputs the received data to standard output.

Sliding Window: The sender maintains a sliding window with a dynamic size, which is updated based on the rate of successful acknowledgements. The window size is increased for successful transmissions and decreased for timeouts.
Selective Repeat: The receiver stores out-of-order packets and acknowledges them when the correct sequence of packets is received.
Adaptive Timeout: The sender adjusts its timeout value based on the calculated round-trip time (RTT) to avoid unnecessary resends and to adapt to changing network conditions.
Challenges Faced
Handling randomly dropped packets: The protocol is designed to handle situations where packets are dropped during transmission. The sender uses a timeout mechanism to detect dropped packets and resends them when necessary.
Calculating and updating the RTT: The sender dynamically calculates the RTT based on the time it takes to receive acknowledgements from the receiver. This helps the sender adapt to changing network conditions and set appropriate timeouts.
Keeping track of packets to resend: The sender maintains a list of packet resend times, allowing it to efficiently determine which packets to resend when timeouts occur.
Features
Checksum Validation: The sender and receiver use Adler-32 checksums to detect and discard corrupted packets.
Sliding Window with Dynamic Size: The sliding window approach allows for efficient transmission and flow control, while the dynamic size adaptation improves performance under varying network conditions.
Adaptive Timeout: The adaptive timeout mechanism allows the sender to better handle changing network conditions and avoid unnecessary packet resends.
Selective Repeat: The selective repeat mechanism in the receiver ensures that only the missing packets are retransmitted, improving overall transmission efficiency.
Testing
The code was tested with a variety of network conditions, including packet loss, corruption, and out-of-order delivery. The tests covered different window sizes and varying data sizes to ensure the protocol could handle a wide range of scenarios. The performance and reliability of the protocol were assessed by monitoring successful packet transmission rates, throughput, and latency under various conditions.
