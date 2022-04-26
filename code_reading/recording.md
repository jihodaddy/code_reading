# 코드본 것(사소한 놓친것 들)

## 변수 초기화
    - 클래스에서는 변수(멤버변수 or 인스턴스변수) : 초기화 안해도 자동으로 초기값 설정됨(ex. 0, null)
    - 메서드에서의 변수(지역변수) : 초기화 안하면 에러 발생
  
## json 데이터 추출시 오류(오류메세지: java.util.LinkedHashMap cannot be cast to List..)
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

## 직렬화/역직렬화
### 직렬화
    - 객체에 저장된 데이터를 I/O 스트림에 쓰기(출력) 위해 연속적인(serial) 데이터로 변환하는 것( 객체 => 문자열로 변환을 의미)
    - 
### 역직렬화
    - I/O스트림에서 데이터를 읽어서(입력) 객체를 만드는 것(문자열 => 객체)
    

### Serializable(직렬화)
- java.io.Serializable 인터페이스를 구현한 클래스만 객체를 직렬화할 수 있음.
- Serializable 인터페이스는 구현해야하는 메소드가 없는, 객체의 직렬화를 명시하는 용도의 마크 인터페이스
- Serializable 인터페이스는 JVM에게 이 클래스가 직렬화될 수 있다는 것을 알려주는 역할

#### 상속(is-a)   

    부모 클래스가 Serializable을 구현하면
        - 자식 클래스는 항상 직렬화가 가능하다.
        - 자식 클래스를 직렬화하면 부모 클래스의 인스턴스 변수도 함께 직렬화된다.   

    자식 클래스만 Serializable을 구현하면
    - 부모 클래스의 인스턴스 변수는 직렬화되지 않는다.
    - 부모 클래스의 인스턴스 변수도 직렬화 대상에 포함하려면 두 가지 방법이 있다.
        1. 조상 클래스가 Serializable을 구현한다.
        2. 직렬화 코드를 직접 구현한다.
#### 포함(has-a)
    클래스가 직렬화할 수 없는 객체를 인스턴스 변수로 참조하고 있으면(변수 타입이 아닌 실제 객체의 타입에 의해 결정됨)
    - 직렬화 불가(NotSerializableException)
    - 직렬화 불가한 인스턴스 변수에는 transient를 붙여 제외하고 직렬화 가능
    
