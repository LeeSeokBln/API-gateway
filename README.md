# 데이터를 받으면 Kinesis datastream으로 전송하기 위한 매핑 템플릿

```
{
  "StreamName": "스트림 이름",
  "Data": "$util.base64Encode($input.body)",
  "PartitionKey": "$context.requestId"
}
```


## vtl의 input 
vtl의 변수는 기본적으로 앞에 '$'을 붙임.
만약 경로 ex/name를 필요로 한다면, 리소스를 만들 때 경로를 {name}으로 해준다. ({}표시는 환경변수)
"EX": $input.params('name')이런 식이며,

```
{
  "students": 
  {
  "seokbin": ["age": 19, "gender": "male"], 
  "ilshin": ["age": 19, "gender":"male"]
  }
}
```
이러한 데이터에서 seokbin의 정보를 보고싶다면, 
$input.path($.students.seokbin)을 하면 seokbin의 age,gender만 나오게 된다.즉 
reqeust에 저런 데이터를 넣고
response에 
```
{
  "students-name": $input.path($.student)
  "student-1-age": $input.path($.students.seokbin.age)
}
```
이런식으로 넣는다면 결과는
```
{
  "students-name": seokbin, ilshin
  "student-1-age": 19
}
```
이렇게 나오게 된다
