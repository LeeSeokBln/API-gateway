# 레코드를 받으면 Kinesis Data stream으로 전송
```
POST / HTTP/1.1
Host: kinesis.<region>.<domain>
Content-Length: <PayloadSizeBytes>
User-Agent: <UserAgentString>
Content-Type: application/x-amz-json-1.1
Authorization: <AuthParams>
Connection: Keep-Alive 
X-Amz-Date: <Date>
X-Amz-Target: Kinesis_20131202.PutRecords
{
    "Records": [
        {
            "Data": "XzxkYXRhPl8x",
            "PartitionKey": "partitionKey1"
        },
        {
            "Data": "f1PxFQo92Afh",
            "PartitionKey": "partitionKey2"
        },
        {
            "Data": "Gi4sEdd08HypA",
            "PartitionKey": "partitionKey3"
        }
    ],
    "StreamName": "exampleStreamName"
}
```
