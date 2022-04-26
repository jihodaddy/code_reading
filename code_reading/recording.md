# 사소한 것들

## 코드본 것(사소한 놓친것 들)
### 변수 초기화
    - 클래스에서는 변수(멤버변수 or 인스턴스변수) : 초기화 안해도 자동으로 초기값 설정됨(ex. 0, null)
    - 메서드에서의 변수(지역변수) : 초기화 안하면 에러 발생
  
### json 데이터 추출시 오류(오류메세지: java.util.LinkedHashMap cannot be cast to List..)
    - Response되는 JSON 데이터를 사용하기 편한 형태로 변경하기 위해서는   
      JSON 데이터를 deserialization(역직렬화) 하여 pojo 형태의 사용하기 편한 객체화 해야 한다.

```java
    JSONParser json = new JSONParser();
    Object obj = json.parse(jsonstr);
    JSONObject jsonObj = (JSONObject)obj;
```

    - 오류원인
        - 변환되는 객체에 어떤 요소가 있어야 하는지 알지 못했을때 Exception 발생
        - JSON에서 개체를 역직렬화 하려고 하지만 유형 정보가 제공되지 않으면 기본 유형인 LinkedHashMap을 사용함   
            - LinkedHashMap 사용해 역직렬화 한뒤 내부 속성 키값의 정보가 일치하지 않았을때 Exception 발생
