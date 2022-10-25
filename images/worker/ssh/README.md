##### Jenkins container connects to the worker via ssh
  - For this generate an SSH key for jenkins controller
    - ``` ssh-keygen -o -a 100 -b 4096 -t ed25519 -f images/jenkins/id_ed25519 -C "jenkins" ```
  - And authorize it by a worker
    - ``` cat images/jenkins/id_ed25519.pub >> images/worker/ssh/authorized_keys ```
  - Don't forget to create SSH credentials for root user via [Jenkins UI](http://localhost:8080/manage/credentials/store/system/domain/_/newCredentials) using generated private SSH key
