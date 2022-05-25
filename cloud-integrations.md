# Cloud Integration
Types of communication:
- Sync: app to app
- Async/event: app to queue to app

Better to decouple when getting traffic:
- SQS: Queue model
- SNS: pub/sub model
- Kinesis: real-time data streaming

They can scale independently.

## Amazon SQS (Simple Queue Service)
Fully managed (serverless); decouple
- Producer => Queue => Consumer
- Scale horizontally
- Up to 14 days

## Amazon SNS (Simple Notificacion Service)
1 message to many receivers (Publisher => SNS Topic => Subscriber). 
- Short duration

## Kinesis
Managed service to **collect, process & analyze** real-time streaming data at any scale
- **Kinesis Data Streams**: low lat streaming to ingest data at sclae form 100s of 1ks of sources
- **Kinesis Data Firehose**: load streams into:
    - S3
    - Redshift
    - ElasticSearch
- **Data Analytics**: perform real-time analytics on streams using SQL
- **Video Streams**: monitor real/time video streams for ML/Analytics

Sources:
- Click streams 
- IoT devices
- Metrics & logs

## Amazon MQ
Open protocols (MQTT, AMQPS, STOMP, Openwire, WSS)
- Managed Apache ActiveMQ
- Migrating from on-premises
- You need to provision, doesn't scale as much
- Runs on a **dedicated machine**
- Has both features (SQS, SNS)