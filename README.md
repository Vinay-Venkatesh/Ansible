# Ansible
Repository used to practice ansible 

# SSH Setup
1. Generate ssh key from client
    ssh-keygen 
2. Create a password file with relevant server passwords.

3. Small logic to copy ssh key of client to other servers.

for user in ansible root 
do
  for os in ubuntu centos
  do
    for instance in 1 2 3
    do
        sshpass -f password.txt ssh-copy-id -o StrictHostKeyChecking=no ${user}@${os}${instance}
    done
  done
done

# Test Connectivity

1. ansible -i,ubuntu1,ubuntu2,ubuntu3,centos1,centos2,centos3 all -m ping
