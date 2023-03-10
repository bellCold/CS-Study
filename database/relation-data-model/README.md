# 관계형 데이터 모델

관계 데이터 모델은 2차원 구조의 테이블 형태를 통해 자료를 표현하는 것을 말합니다.

***관계형 데이터 모델의 용어***

- 릴레이션(Relation): 데이터들을 2차원 테이블의 구조로 저장한 것 -> table
- 튜플(Tuple): 릴레이션의 행(=Row). 속성들의 집합이며 레코드(Record)라고도 부릅니다.
- 속성(Attribute): 릴레이션의 열(=Column), 개체를 구성하는 속성들을 나타냅니다. -> field
- 차수(Degree): 릴레이션을 구성하는 속성의 수 -> field 수
- 카디널리티(Cardinality): 릴레이션에 입력된 튜플의 수 -> 레코드 수
- 도메인(Domain): 하나의 속성이 가질 수 있는 값들의 범위
- 널(Null): 정보 부재를 나타내기 위해 사용되는 특수한 데이터 값

---

***릴레이션의 특징***

- 튜플 사이에는 순서가 없다.

- 튜플들의 삽입, 삭제 등의 작업으로 인해 릴레이션은 시간에 따라 변합니다.

- 속성들 간의 순서는 중요하지 않습니다.

- 속성의 유일한 식별을 위해 속성의 명칭은 유일해야 하지만, 속성을 구성하는 값은 동일한 값이 있을 수 있습니다.

- 릴레이션을 구성하는 튜플을 유일하게 식별하기 위해 속성들의 부분집합을 키(Key)로 설정합니다

- 속성의 값은 논리적으로 더 이상 쪼갤 수 없는 원자 값만을 저장합니다. 1개만

---

***릴레이션 키 다섯가지(유일성과 최소성)***

키는 데이터베이스에서 조건에 만족하는 관계의 행을 찾거나 순서대로 정렬할 때 다른 행과 구별할 수 있는 유리한 기준이 되는 속성의 집합이다.

* 슈퍼키
    * 테이블에서 각 행을 유일하게 식별할 수 있는 하나 또는 그 이상의 속성들의 집합이다. 슈퍼키는 <u>유일성</u>만 만족하면 슈퍼키가 될 수 있다.
* 후보키
    * 각 행을 유일하게 식별할 수 있는 <u>최소한</u>의 속성들의 집합이다.
* 기본키
    * 후보키들 중에서 하나를 선택한 키로 최소성과 유일성을 만족하는 속성이다.
* 보조키(대체키)
    * 후보키가 두개 이상일 경우 그 중에서 어느 하나를 기본키로 지정하고 남은 후보키들을 대체키라한다.
* 외래키
    * 테이블이 다른 테이블의 데이터를 참조하여 테이블간의 관계를 연결하는 것이다. 데이터를 좀더 조회하기 쉽다.
    * 다른 테이블의 데이터를 참조할 때 없는 값을 참조할 수 없도록 제약을 주는 것이다.

---

***무결성 (Integrity)이란?***

* 무결성이란 데이터의 정확성, 일관성을 나타냅니다.
* 데이터에 결함이 없는 상태, 즉 데이터를 정확하고 일관되게 유지하는 것을 의미합니다.

***무결성 제약조건***

무결성 제약조건이란 데이터베이스의 정확성, 일관성을 보장하기 위해 저장, 삭제, 수정 등을 제약하기 위한 조건을 뜻합니다.

* 도메인 제약조건
    * 원자값
    * 값의 유형(Type)
    * Check 값의 범위 제한
    * 속성들의 값은 정의된 도메인에 속한 값이어야 합니다.
* 키 제약조건
    * 각 릴레이션은 최소한 한 개 이상의 키가 존재해야 합니다.
* 엔티티 무결성 제약조건
    * 각 릴레이션의 기본키를 구성하는 속성은 널(NULL) 값이나 중복된 값을 가질 수 없습니다.
* 참조 무결성 제약조건
    * 외래키 값은 NULL이거나 참조하는 릴레이션의 기본키 값과 동일해야 합니다.

---

***삭제 , 수정***

* 삭제
    * error
    * cascade
    * null
    * default
* 수정
