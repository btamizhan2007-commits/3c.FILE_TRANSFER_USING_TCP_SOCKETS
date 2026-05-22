# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM:
## DEVELOPED BY : TAMIZHAN B
## REF NO: 212225230283
## SERVER:
```
import socket 
 
# Create socket 
server = socket.socket() 
 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
 
# Listen for client 
server.listen(1) 
 
print("Server waitng for connecton...") 
 
# Accept client 
client, addr = server.accept() 
 
print("Connected to:", addr) 
 
# Ask flename 
flename = input("Enter fle name to send: ") 
 
# Open and send fle 
with open(flename, "rb") as fle: 
 
    data = fle.read() 
 
    client.send(data) 
 
print("File sent successfully") 
 
# Close connectons 
client.close() 
server.close() 
```
## CLIENT:
```
import socket 
 
# Create socket 
client = socket.socket() 
 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
 
# Save fle name 
save_name = input("Enter name to save fle: ") 
 
# Receive data 
data = client.recv(1000000) 
 
# Save fle 
with open(save_name, "wb") as fle: 
 
    fle.write(data) 
 
print("File received successfully") 
 
# Close connecton 
client.close() 
```
## OUPUT:
<img width="1477" height="695" alt="cn 3c server" src="https://github.com/user-attachments/assets/6ad67437-3da6-4bfc-9740-50f903c204b1" />

<img width="1465" height="695" alt="cn3c c" src="https://github.com/user-attachments/assets/f0f8d4e0-215d-4e0a-a947-701864bd3046" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
