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
