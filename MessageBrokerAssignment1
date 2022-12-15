import json
import boto3

def lambda_handler(event, context):
     client = boto3.client("sqs")
     for x in range(500):
      # inititialising json object.
         ini_string = {'Name': 'Navneet', 'Email' : 'nsg@gmail', 'MessageBody' : 'This is Body', 'MessageNumber' : '1'}
         ini_string['MessageNumber']="{}".format(x)
         print(ini_string)
         serialize = json.dumps(ini_string)
         response = client.send_message(
         QueueUrl="https://sqs.us-east-1.amazonaws.com/772164543109/navneetgaur_1", 
         MessageBody=serialize
         )

     print(response)
 
     return {
         'statusCode': response["ResponseMetadata"]["HTTPStatusCode"],
         'body': json.dumps(response["ResponseMetadata"])
    }
