# Apache-Kafka--Exercise-
Problem 1 :
Write a Kafka producer that will read “1500000SalesRecords.csv” file line by line and convert each line to JSON and send the data to a Kafka topic. 
The name of the topic should be “test.topic.raw”. 

Problem 2:
Write a Kafka consumer that will read data from the topic named “test.topic.raw”. It should read the data from the beginning  and do the below filtering of data:
Select only those data whose “Total Cost” value is greater than 304017.56
After selection, it should send the filtered data to another topic named “test.topic.threshold_costs”

Problem 3:
Write a Kafka consumer that will read data from multiple topics:
The name of the topics is "test.topic.raw" and "test.topic.threshold_costs"
They should also read data from the beginning of the topic
Filter the data based on the country and send data to different topic depending on country value “test.topic.{country}". For each country, a new topic needs to be created and data needs to be sent to the corresponding topics. So, if there is some data for the country Cuba, then a topic named test.topic.cuba should be created and the data should be sent to this topic. Similarly for other countries. You need not create separate topics for each country using the command line.  Think of some logic to implement it using python code only.
When you list all the topics, you will see that the topics are created for each country
The command to list all the topics is as follows.

bin/kafka-topics.sh --bootstrap-server localhost:9092 --list

Problem 4 :
Write down 2 Kafka consumers, both reading data from the same topic “test.topic.raw”. Both consumers should receive the same messages and do as described ahead.

 Consumer1 should do the following:
Get the “Sale Channel” from JSON data
Send data to a  Kafka topic depending on the channel of the sale. If for a sale the channel is offline then that data should be sent to a topic named test.topic.offline. So, for each unique sale channel, a separate topic has to be created
List the topics, you should see all the topics created for each Sale Channel
As you can see in the image below topics named test.topic.offline and test.topic.online has been created.

 Consumer2 should do the following:
Filter the data based on Unit Cost
Send data to Kafka topic named “topic.costly_order” if ‘Unit Cost’ is more than “10000” 
Start consumer console to verify data reaching to the given topic.


