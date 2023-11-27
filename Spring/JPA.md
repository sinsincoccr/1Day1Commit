# JPA <br/>


- JPA Java Persistence Api : 자바 기반의 ORM 기술 표준
- ORM Object-Relational Mapping : 객체와 관계형데이터베이스를 매핑한다는 뜻.
- ORM 프레임워크는 객체와 데이블을 매핑해서 패러다임의 불일치 문제를 개발자 대신 해결해준다.
- EJB Enterprise Java Bean : 엔티티 빈이라는 ORM 기술이 포함된 과저 자바 기술 표준으로 너무 복잡하고 사용하기 어려웠음 -> Hibernate 오픈소스 ORM 탄생
- Hiberante : 오픈소스 ORM 프레임워크로 EJB 보다 가볍고 실용적이며 호환성도 높아 많이 사용됨.
- 결국 EJB 3.0 에서 Hibernate 기반으로 새로운 자바 ORM 기술 표준이 만들어 졌는데 그것이 JPA 이다.
- 표준은 인터페이스들의 묶음이다. 즉 JPA 표준을 사용하기 위해서는 JPA를 구현한 구현체가 필요
- 구현체는 Hibernate, EclipseLink, DataNucleus 등이 있는 Hibernate 가 가장 대중적이다.


### JPA를 사용해야하는 이유
- 생산성
- 유지보수
- 패러다임 불일치 해결
- 성능
- 벤더 독립성

### JPA 구동 방식
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/17f187e1-4cf2-46c5-84af-d26bc93da879)


### JPA 영속성 컨텍스트
- 엔티티를 영구히 저장하는 환경
- 엔티티 매니저(EntityManager)를 생성할 때 영속성 컨텍스트가 하나 만들어 짐
엔티티 매니저를 통해 영속성 컨텍스트에 접근함
- 엔티티 매니저로 엔티티를 저장하거나 조회하면 엔티티 매니저는 영속성 컨텍스트에 엔티티를 보
관하고 관리함
em.persist(member);
-> 엔티티 매니저를 이용해 회원 엔티티를 영속성 컨텍스트에 저장한다
