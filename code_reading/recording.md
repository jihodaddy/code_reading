# 사소한 것들

## 코드본 것(사소한 놓친것 들)
### 변수 초기화
    - 클래스에서는 변수(멤버변수 or 인스턴스변수) : 초기화 안해도 자동으로 초기값 설정됨(ex. 0, null)
    - 메서드에서의 변수(지역변수) : 초기화 안하면 에러 발생
  
### json 데이터 추출시 오류(오류메세지: java.util.LinkedHashMap cannot be cast to List..)
  - 역직력화 할 클래스에 대한 정보가 충분하지 않은 경우 LinkedHashMap 
