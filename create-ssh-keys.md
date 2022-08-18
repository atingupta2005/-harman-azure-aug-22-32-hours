# Generate SSH Keys
mkdir mysshkeys
cd mysshkeys
ssh-keygen -f demo_id_rsa_2

# For Windows: Copy SSH Keys to the VM
cat  demo_id_rsa_2.pub | ssh atingupta2005@20.85.241.216 'mkdir -p .ssh; touch .ssh/authorized_keys; cat >> .ssh/authorized_keys'

# For linux: Copy SSH Keys to the VM
ssh-copy-id -i ~/.ssh/demo_id_rsa_2.pub atingupta2005@20.85.241.216

# Connect to VM
ssh -i demo_id_rsa_2 atingupta2005@20.85.241.216
