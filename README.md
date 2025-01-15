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
Get into the folder we just created
```bash
cd kafka
```
