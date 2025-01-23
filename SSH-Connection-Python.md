## Start Connection (Regular User)

```python
import paramiko

class ClassName:
	def __init__(self, target_ip):
		self.target_ip = target_ip
		self.ssh_client = None 
		
	def connect_ssh(self, username, password):
		try :
			self.ssh_client = paramiko_SSHClient()
			self.ssh_client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
			self.ssh_client.connect(self.target_ip, username=username, password=password)
			return True
		except Exception as e:
			print(f"SSH Connection failed: {e}") 
			return False
```

## Start Connection (Root User)

```python
import paramiko
import time  
class ClassName:
    def __init__(self, target_ip):
        self.target_ip = target_ip
        self.ssh_client = None

    def connect_ssh(self, username, password):
        try:
            self.ssh_client = paramiko.SSHClient()
            self.ssh_client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
            self.ssh_client.connect(self.target_ip, username=username, password=password)
            
            channel = self.ssh_client.get_transport().open_session()
            channel.get_pty()
            channel.exec_command('sudo -S -p "" /bin/bash')
            channel.send(password + '\n')
            time.sleep(1)
            
            return True
        except Exception as e:
            print(f"SSH Connection failed: {e}")
            return False
```
