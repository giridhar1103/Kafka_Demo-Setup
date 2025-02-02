# Kafka_Demo-Setup
A basic repo to demonstrate kafka setup.

## On EC2 instances
I have used the t2 micro (free trial) to demonstrate the setup.
SSH into your instance by using EC2 instance connect/putty etc.
Once you're into the terminal enter the command:

```bash
sudo apt update && sudo apt upgrade -y
```
Then install java, which is a prerequisite to install kafka
I'm using version 11 because it's compatible and stable right now. 

```bash
sudo apt install openjdk-11-jdk -y
```
To double check if you have installed:

```bash
java -version
```
I will be demonstrating kafka with the help of python so we will install kafka-python to communicate with the brokers.
```bash
pip install kafka-python
```

Now let's install kafka:
Go to https://downloads.apache.org/kafka/ and find the desired version of kafka.
Copy the link to that file (should end with .tar) and attach it to this command:
```bash
wget https://downloads.apache.org/kafka/3.8.0/kafka_2.13-3.8.0.tgz
```
Then extract it
```bash
tar -xvzf kafka_2.13-3.8.0.tgz
```
```bash 
mv kafka_2.13-3.5.0 kafka
```
Get into the folder that we just extracted:
```bash
cd kafka
```
To edit the server.properties file, you need root access. Which can be done by:
```bash
sudo su
```

Edit the server.properties file to allow all external traffic
```bash
nano config/server.properties
```
Find these lines and edit them according to your details. You can come back to this later if you want to limit the listening.
```bash
#Using this we can listen on all IP addresses
listeners=PLAINTEXT://0.0.0.0:9092
```
```bash
#Advertises your public EC2 IP address to external clients
advertised.listeners=PLAINTEXT://<your-ec2-public-ip>:9092
```
Save the file by pressing ctrl+x. Save modified buffer? -> Yes -> Enter 

Note: You need to change this IP address everytime you stop or terminate your AWS EC2 instance. Which means you have to repeat this step everytime you stop/terminate or create a new instance as IP addresses are dyinamic in AWS EC2. 
An alternative to this would be, using the Elastic IP address which remains constant no matter what you do with your EC2 instance (You can even assign it to different instances). But this does not come under the AWS free tier as of 2025. 

