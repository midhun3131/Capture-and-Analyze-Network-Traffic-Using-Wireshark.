# Capture-and-Analyze-Network-Traffic-Using-Wireshark.
# 1. Install Wireshark
Go to Wireshark.org/download1. Update Your Package List
1. Update Your Package List
sudo apt update
2. Install Wireshark
sudo apt install wireshark -y
3. Allow Non-Root Users to Capture Packets (Optional but Recommended)
If you don’t do this, you’ll need to run sudo wireshark every time.
sudo dpkg-reconfigure wireshark-common
sudo usermod -aG wireshark $USER
Then log out and log back in for changes to apply.
4. Verify Installation
wireshark --version
5. Run Wireshark
wireshark
If you want to start capturing without opening the GUI (CLI mode), you can use:
tshark
# Start Capturing
Click on your chosen interface → Wireshark will start capturing packets live.
You’ll see lines scrolling with packet details
Time (timestamp)
Source and Destination IPs
Protocol (e.g., TCP, DNS, HTTP)
Info (summary of packet content)
#  Generate Some Traffic
Open a browser and visit a few websites
open Command Prompt/Terminal and run:
ping google.com
This ensures Wireshark captures multiple types of traffic.
# Stop Capture
Let it run for about 1 minute.
Click the red square Stop button in Wireshark.
# Filter by Protocol
In the top filter bar:
Type http → press Enter → see only HTTP packets.
Type dns → press Enter → see only DNS packets.
Type tcp → press Enter → see only TCP packets.
You can also use icmp to see ping traffic.
# Identify at Least 3 Protocols
Typical ones you’ll see:
DNS – for domain name lookups.
HTTP/HTTPS – for web browsing.
TCP – for reliable data transfer.
ICMP – for ping.
ARP – for local device discovery.
#  Export the Capture
Go to File → Save As.
Save it as .pcapng or .pcap (both work).
Name it something like network_capture.pcap.
# 
