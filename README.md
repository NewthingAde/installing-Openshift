# installing-Openshift

                     sudo apt-get update
                     
                     sudo apt-get install \
                        ca-certificates \
                        curl \
                        gnupg \
                        lsb-release
                      
                      sudo mkdir -p /etc/apt/keyrings
                      
                      curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
                      
                      echo \
                    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
                    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
                    
                     sudo apt-get update
                     
                    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin


Download the file using the command 

          wget https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
    --2022-10-14 20:05:46--  https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz

                tar xvzf openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
                
Cd in to `openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit`



Use the following command 

              sudo oc cluster  up

Add the following command to the `vi /etc/docker/daemon.json`

              { "insecure-registries": ["172.30.0.0/16"] }
              
              sudo systemctl reload-daemon
              
              sudo sytemctl restart docker
              
              
