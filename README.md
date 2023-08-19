<p align="center">
<img src="https://github.com/itsims007/Capturing-packets-and-using-filters/assets/105188024/8da1e134-7d14-4446-967c-7ddc27fbfea6)"alt="wiresharklogo"/>
</p>
<h2>Using WireShark to Capture-packets-and-use-filters</h2>

<h2>Task 1</h2>

  -Install and set up Wireshark on Ubuntu:

  -To get the latest stable version of Wireshark on Ubuntu Linux, use the add-apt-repository command: sudo add-apt-repository ppa:wireshark-dev/stable

  -Wireshark should not be run as superuser for security reasons.

  -The user can be added to the Wireshark group to add packet capture capabilities: sudo usermod -aG wireshark $USER


<h2>Task 2</h2>

Start a packet capture on an ethernet port and save it to file:

  -The wired interface includes the ethernet packet capture, which begins with ‘en’ in Wireshark.

  -The Wireshark app includes controls to start packet capture, stop capture, save the packets to a file, and load the capture file.

  -A capture can only be saved once the capture has stopped.

<h2>Task 3<h2>

  -Use a display filter to detect HTTPS packets:

  -To display certain packets in an existing packet capture, use a display filter.

  -To display only HTTPS traffic, use a filter on TCP port 443: tcp.port == 443

<h2>Task 4<h2>

  -Visit a web page and detect its IP address using a display filter:

  -A TLS handshake display filter may be used to detect a website visit in a packet list: tls.handshake.type ==1

  -The IP address is used in a filter to obtain packet information for a particular website: ip.addr == 142.251.163.105

<h2>Task 5<h2>

  -Locate all HTTPS packets from a capture not containing a certain IP address:

  -A Conditional statement may be used to include and eliminate packets from a Wireshark capture: !(ip.addr == 8.43.85.97) and tcp.port == 443

  -A compound conditional should include parentheses to avoid order of execution errors: !(ip.addr == 8.43.85.97) and (tcp.port == 80 or tcp.port == 443)
