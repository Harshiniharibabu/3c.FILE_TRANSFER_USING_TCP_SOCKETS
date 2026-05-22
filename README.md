# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM

SERVER:
````
import socket
server = socket.socket()
server.bind(("127.0.0.1", 5555))
server.listen(1)
print("Server waiting for connection...")
client, addr = server.accept()
print("Connected to:", addr)
filename = input("Enter file name to send: ")
with open(filename, "rb") as file:
 data = file.read()
 client.send(data)
print("File sent successfully")
client.close()
server.close()
````
CLIENT:
````
import socket
client = socket.socket()
client.connect(("127.0.0.1", 5555))
save_name = input("Enter name to save file: ")
data = client.recv(1000000)
with open(save_name, "wb") as file:
 file.write(data)
print("File received successfully")
client.close()
````
## OUTPUT

<img width="1858" height="977" alt="Screenshot 2026-05-22 133016" src="https://github.com/user-attachments/assets/2088c84b-256b-46fa-85ed-315ad318388c" />



<img width="1843" height="975" alt="Screenshot 2026-05-22 133104" src="https://github.com/user-attachments/assets/2a3b6d7a-8618-423e-b592-d8cd4a709a8f" />




## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
