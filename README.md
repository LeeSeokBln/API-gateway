# 데이터를 받으면 Kinesis datastream으로 전송하기 위한 매핑 템플릿

```
{
  "StreamName": "스트림 이름",
  "Data": "$util.base64Encode($input.body)",
  "PartitionKey": "$context.requestId"
}
```
