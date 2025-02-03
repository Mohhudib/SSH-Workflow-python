class SSHWorkflow:
    def __init__(self, server_ip, port):
        self.server_ip = server_ip
        self.port = port
        self.shared_secret = None
        self.encryption_key = None

    def initiate_connection(self):
        print(f"Connecting to {self.server_ip}:{self.port}...")
        print("Connection established.")
        return True

    def key_exchange(self):
        self.shared_secret = "shared_secret_placeholder"
        print("Key exchange completed.")
        return self.shared_secret

    def establish_secure_session(self):
        self.encryption_key = self.shared_secret[:32]
        print("Secure session established.")
        return self.encryption_key

    def transmit_data(self, data):
        encrypted_data = "encrypted_" + data
        print("Data encrypted and sent.")
        return encrypted_data

    def terminate_session(self):
        print("Connection closed.")

# Example Workflow
if __name__ == "__main__":
    ssh = SSHWorkflow("127.0.0.1", 22)

    if ssh.initiate_connection():
        ssh.key_exchange()
        ssh.establish_secure_session()
        data = "Hello, Secure World!"
        ssh.transmit_data(data)
        ssh.terminate_session()
