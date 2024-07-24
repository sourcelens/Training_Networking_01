'''
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind(("127.0.0.1", 65432))
s.listen()
conn, addr = s.accept()
print(f"Connected by {addr}")
data = conn.recv(1024)         
conn.sendall(data + b" from server")
conn.close()
print("going to end here")
'''
