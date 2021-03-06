# Oracle

__충분히 큰 예산과 복잡한 비즈니스 요구와 기업 고객을 위해 설계__

- 유닉스 환경에서 가장 널리 사용되는 RDBMS
- 대량의 정보 관리를 할 때에 가장 좋은 성능

# Mssql

__Windows에 특화되어 있는 데이터베이스__  

- 기업에서 사용하려면 라이센스 지불 해야함
- C# 등의 Windows 언어와 호환성이 좋음

# Mysql

__일반적으로 데이터베이스 기반 웹 사이트 및 Non-Critical 어플리케이션에 사용되는 저가의 데이터베이스__

- 사용하기가 다른 DBMS들보다 쉽다
- PHPMyAdmin같은 무료 GUI툴이 많다
- 오버헤드가 적다(1mb RAM만 사용 / 오라클은 128mb)
- 고급기능(Stored Procedures, Triggers, View, Sub-Queries, Transactional Table, Cascading Update & Delete) 의 지원이 시작됨
- 오라클에 인수되면서 __상업적으로 사용할 시 유료__ 이다.

# MariaDB

- 리눅스 진영에서 Mysql 대신에 표준으로 채택함.

## Mysql과 MariaDB의 차이

- MariaDB 오픈소스 개발이 조금 더 개방적이고 활발함
- Mysql도 교육, 개발용인 커뮤니티 버젼은 무료로 제공하지만, 실제 서비스에 사용하기에는 성능이 따라주지 않는다.

# PostgreSQL

__복잡한 쿼리를 실행해야 하는 환경에서 뛰어난 RDBMS__ 

- 매번 새로운 프로세스를 포크하여 사용하기 때문에 메모리의 오버헤드가 있다. 즉, 복잡한 쿼리를 처리하는데에 있어선 성능이 좋기때문에 알맞지만 간단한 읽기 작업의 경우 성능이 떨어진다.

# MongoDB

__NoSQL DB이다. 규정된 스키마가 없기에 필드가 항상 달라질수 있음__ 

## 총평

Oracle과 Mssql은 라이센스 구매시 비용을 지불해야 하기 때문에, 웹 서비스 구축같은곳에는 쓰이지 않는다. __대규모 프로젝트에서 주로 쓰임__ (오라클은 그중에서도 인터넷 뱅킹, 보험, 통신 등 돈이 많이 오가는 업무에서 많이 사용)   

중소기업이나 작은 규모의 프로젝트에서는 무료 데이터베이스 SW를 많이 사용  

## RDB vs Nosql DB

관계형 데이터베이스는 엄격한 스키마에 따라 테이블에 레코드가 저장된다. 이를 준수하지 않는 레코드들은 추가될 수 없다.  

SQL 기반의 데이터베이스, RDB는 __데이터들을 여러개의 테이블에 나누어, 데이터들의 중복을 피할 수 있다.__  이러한 명확한 구조를 통해, 하나의 테이블에는 중복없이 데이터들을 관리하기 때문에, 다른 테이블에서 부정확한 데이터를 다룰 위험이 없다.  

NoSQL은 스키마가 없고, 관계가 없다. 여기서는 레코드가 문서로 불린다. 정해진 스키마를 따르지 않아도, 같은 컬렉션(테이블)에 추가할 수 있다.  

문서(레코드)는 JSON 데이터와 비슷한 형태를 가진다.

```
-> 명확한 스키마를 가지고 있고, 데이터가 자주 변경되는 경우 SQL  

-> 정확한 데이터 구조를 모르고, Read는 많이 하지만 Update는 많이 하지않는 경우 NoSQL, DB를 수평으로 확장해야 하는 경우(막대한 양의 데이터를 다뤄야 할 때)  
```