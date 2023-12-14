# Part 1: Synthesis of continuous time control systems. The gain and phase margin. Linear systems and their description in time- and frequency domains. Signal transfer in control systems.

## Control Systems:

- A control system is a system that provides the desired response by controlling the output. The input is varied by some mechanism. The traffic lights control system is an example of a control system. 


- Control systems can be classified on the type of signal. A system that deals with continuous-time signals is called a continuous-time system; its opposite is the discrete-time system which uses discrete-time signals. 

- Continuous time control system uses continuous signals that vary with time as inputs and outputs.

- Synthesis aims to stabilize the system, reduce errors and improve performance and robustness. 

- Synthesis techniques include classical methods such as PID control and modern control methods such as space-state and optimal control. 

- Trade-offs between stability, performance, robustness and complexity are considered.
- Synthesis of continuous-time control systems involves designing controllers that can regulate and stabilize a given system. This process typically includes analyzing the system's characteristics, such as gain and phase margins, and describing the system in both time and frequency domains. Signal transfer in control systems refers to the flow of signals from the input to the output of the control system.

## Gain and Phase Margin:
- The Gain and Phase Margin can be determined from bode plot. 

- A Bode Plot is a graph the is used to determine the stability of a control system. It maps the frequency response of the system throughout 2 graphs: Bode Magnitude plot (decibels), Bode Phase Plot (degrees).  

Gain Margin  | Phase Margin
---|---|
It measures the amount of gain that can be increased or decreased without causing instability. | Represents the amount of phase that can be increased or decreased without causing instability. 
A longer gain margin indicates a more stable system. | A higher phase margin indicates a more stable system. 
GM can be calculated from the difference between the magnitude curve and the x-axis at the phase crossover frequency on the bode plot. | PM can be calculated from the difference between  phase curve and the x-axis at the gain crossover frequency on the bode plot.


## Linear Systems and Time/Frequency Domains:
- Linear systems are systems whose outputs for a linear combination of inputs are the same as a linear combination of individual responses to those inputs. 
- Linear systems can be time-invariant which are linear systems where the output does not depend on when input was applied. So, if we apply an input to a system now or T seconds from now, the output will be identical except for a time delay of T seconds. 
- Linear systems in frequency domains refer to the analysis of these systems with respect to frequency. A frequency-domain graph shows how much of the signal lies within each given frequency band over a range of frequencies.
- To change a linear system from a time domain to a frequency domain, we apply a Laplace transform function of the impulse response. In the frequency domain, the output is the product of the transfer function with the transformed input. 
- Linear control systems use negative feedback to produce a control signal to maintain the controlled PV (Process Variable) at the desired SP (setpoint). There are several types of linear control systems with different capabilities.
## Signal Transfer in Control Systems:
__Signal transfer in control systems:__  
Refers to the transmission, manipulation, and flow of signals within the system to convey information about the system's state and control objectives.
Involves the relationship between the input and output signals of a control system.
The transfer function is a crucial mathematical representation of this relationship.

__The transfer function:__  
Quantifies how the system responds to different input signal frequencies.
It is defined as the ratio of the Laplace transform of the output variable to the Laplace transform of the input variable, assuming all initial conditions are zero.
Allows various types of input and output signals to be represented in a standardized mathematical framework.

__Methods to obtain the transfer function:__  
Block diagram method and signal flow graph provide graphical representations of the transfer function.
These methods simplify the analysis and design of control systems.

__Poles and zeros of the transfer function:__  
- Poles represent values that make the transfer function infinite.
- Zeros represent values that make the transfer function zero.

They play a significant role in determining the behavior of the transfer function.

__Calculating the transfer function:__  
Write the time-domain equations of the system, considering the required variables.
Obtain the Laplace transform of these equations.
Determine the input and output variables from the frequency domain equations.
Manipulate the equations and consider the initial conditions to calculate the transfer function as the ratio of the Laplace transform of the output and input variables.

# Part 2: Explain the data elements of TCP and UDP transport layer protocols, and the differences between their mechanisms.
TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are two widely used transport layer protocols in computer networks. They serve as the foundation for data transmission between applications running on different devices.

## Data elements:

![image](https://github.com/Darwish-md/State-Exam-2023/assets/72353586/d63f6ad0-cb9a-42ad-bf94-9fe6e7aa8e64)

### TCP
- __Source Port:__ This 16-bit field identifies the sending application or process within the source device.

- __Destination Port:__ Similar to the source port, this 16-bit field identifies the receiving application or process within the destination device.

- __Sequence Number:__ This 32-bit field is used to maintain the order of the data segments transmitted from the source to the destination. It allows the receiving end to reconstruct the data in the correct order.

- __Acknowledgment Number:__ Also a 32-bit field, it serves as a positive acknowledgment from the receiving end, indicating the sequence number of the next expected data segment.

- __Window Size:__ This 16-bit field specifies the number of data bytes that the sender is willing to send before receiving an acknowledgment. It helps in flow control and avoids overwhelming the receiver.

- __Checksum:__ A 16-bit field that ensures the integrity of the TCP segment by verifying the correctness of the transmitted data. The calculation of the checksum involves the following steps:
  - The data to be transmitted is divided into a series of words (usually 16 bits or 32 bits).
  - These words are then summed together, typically using one's complement arithmetic.
  - The resulting sum is complemented (bitwise negated) to obtain the checksum value.

- __Urgent Pointer:__ If the URG (urgent) flag is set, this 16-bit field points to the sequence number of the last urgent data byte in the TCP segment.

- __Options:__ This variable-length field allows for additional TCP functionality, such as setting maximum segment size, timestamping, and window scaling.

***Examples: Web Browsing, Email, File Transfer, Remote Desktop Protocol, Database Access***

### UDP
- __Source Port:__ Similar to TCP, this 16-bit field identifies the sending application or process within the source device.

- __Destination Port:__ Like TCP, this 16-bit field identifies the receiving application or process within the destination device.

- __Length:__ This 16-bit field specifies the length of the UDP datagram, including the header and the data.

- __Checksum:__ A 16-bit field that ensures the integrity of the UDP datagram by verifying the correctness of the transmitted data.

***Examples: Real-Time Streaming, DNS, IoT, DHCP***

## Mechanisms:

- __Connection-Oriented vs. Connectionless:__ TCP is connection-oriented, meaning it establishes a reliable, ordered, and error-checked connection between the sender and receiver. UDP, on the other hand, is connectionless, providing a best-effort delivery mechanism without establishing a connection or ensuring reliability.

- __Flow Control and Congestion Control:__ TCP incorporates flow control and congestion control mechanisms to manage the rate of data transmission and avoid network congestion. UDP does not provide these mechanisms.

- __Reliability:__ TCP guarantees reliable data delivery by using acknowledgment, retransmission, and error-checking mechanisms. UDP does not provide any built-in mechanisms for reliability, making it more suitable for applications where real-time or low-latency communication is prioritized over guaranteed delivery.

- __Overhead:__ Due to its additional functionality for reliability and flow control, TCP has higher overhead in terms of header size and computational requirements compared to UDP, which has a minimal header.

- __Ordering:__ TCP ensures in-order delivery of data segments, while UDP does not guarantee the order of data delivery. UDP is more appropriate for applications where real-time data is more critical than maintaining strict ordering.

  ![image](https://github.com/Darwish-md/State-Exam-2023/assets/72353586/521e79ad-fa11-47e0-be43-04e56fa5ceb3)

## three-way handshake
The three-way handshake is a method used in TCP (Transmission Control Protocol) to establish a connection between a client and a server. It ensures that both the client and server are ready to send and receive data before the actual transmission begins. Let's walk through the three-way handshake process with an example:

1. Client (C) sends a SYN packet to the server (S):  
***C: SYN = 1, Sequence Number = X***  
 This packet is sent by the client to initiate the connection. The SYN flag is set to 1 to indicate that the client wants to synchronize and establish a connection. The Sequence Number is set to X, which is a randomly chosen initial sequence number.

2. Server (S) receives the SYN packet and responds with a SYN-ACK packet:  
***S: SYN = 1, ACK = 1, Sequence Number = Y, Acknowledgment Number = X + 1***   
The server receives the SYN packet and acknowledges it by sending a SYN-ACK packet back to the client. The SYN flag is set to 1 to indicate synchronization, and the ACK flag is set to 1 to acknowledge the client's SYN packet. The server chooses its own initial sequence number Y, and the Acknowledgment Number is set to the client's initial sequence number (X) incremented by 1.

3. Client (C) receives the SYN-ACK packet and sends an ACK packet to the server:  
***C: ACK = 1, Sequence Number = X + 1, Acknowledgment Number = Y + 1***  
 The client receives the SYN-ACK packet from the server, confirming that the server is ready to establish a connection. The client responds by sending an ACK packet to acknowledge the server's SYN-ACK packet. The ACK flag is set to 1, and the Sequence Number is set to the client's initial sequence number (X) incremented by 1. The Acknowledgment Number is set to the server's initial sequence number (Y) incremented by 1.

At this point, the three-way handshake is complete. The client and server have exchanged SYN, SYN-ACK, and ACK packets, confirming their readiness to establish a connection. They have agreed on initial sequence numbers and acknowledged each other's packets.

After the three-way handshake, both the client and server can begin sending and receiving data over the established connection. The sequence numbers and acknowledgment numbers are used to ensure reliable and ordered delivery of data packets between the client and server.