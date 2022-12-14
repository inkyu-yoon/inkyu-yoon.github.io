---
layout: post
title: "· JPA 기본 어노테이션과 EntityManager 메서드"
nav_order: 1
parent : JPA
grand_parent: 👩🏻‍💻Language
permalink: docs/Language/JPA/JPABasic
---

# JPA 기본 어노테이션과 메서드
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---



# JPA 기초



## 환경설정

<br>

스프링 부트를 사용하지 않는 순수 JPA 환경설정에 대해 알아보겠다.

- JPA 하이버네이트 라이브러리를 추가한다. (혹은) jpa 라이브러리 추가

```java
	<dependency>
        <groupId>org.hibernate</groupId>
        <artifactId>hibernate-entitymanager</artifactId>
        <version>5.3.10.Final</version>
    </dependency>
```

- 순수 JPA를 사용하기 위해서는 `persistence.xml` 설정파일이 필요하다.

-> 설정 파일의 위치는 반드시 resource 폴더의 **/META-INF/persistence.xml**  위치에 있어야한다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221031233423438.png" alt="image-20221031233423438" style="zoom:80%;" />
</p>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="2.2"
             xmlns="http://xmlns.jcp.org/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence http://xmlns.jcp.org/xml/ns/persistence/persistence_2_2.xsd">
<!--    EntityManagerFactory 객체 생성시 참고해야할 persistence 이름 -->
    <persistence-unit name="hello"> 
        <properties>
            <!-- 필수 속성 사용하는 db, 패스워드, 버전에 따라 적절한 값 입력  -->
            <property name="javax.persistence.jdbc.driver" value="org.h2.Driver"/> 
            <property name="javax.persistence.jdbc.user" value="sa"/>
            <property name="javax.persistence.jdbc.password" value=""/>
            <property name="javax.persistence.jdbc.url" value="jdbc:h2:tcp://localhost/~/test"/>
            <property name="hibernate.dialect" value="org.hibernate.dialect.H2Dialect"/>

            <!-- 옵션 -->
            <property name="hibernate.show_sql" value="true"/>
            <property name="hibernate.format_sql" value="true"/>
            <property name="hibernate.use_sql_comments" value="true"/>
            <!--<property name="hibernate.hbm2ddl.auto" value="create" />-->
        </properties>
    </persistence-unit>
</persistence>
```

그리고 위와 같이 `persistence.xml` 파일을 채운다. `jdbc.driver`와 `hibernate.dialect` 부분은, 어떤 데이터베이스를 사용하느냐에 따라 달라질 수 있는 부분이다.

주목해야할 부분은 **persistence-unit name을 "hello"로 지정했다는 것이다.**

jpa를 통해 데이터를 관리하려면 `EntityManager` 객체의 다양한 메서드를 사용해야하는데, 위 unit name을 통해서

`EntityManagerFactory emf = Persistence.createEntityManagerFactory("hello");`

로 `EntityManagerFactory` 를 먼저 생성한 후, 

`EntityManager em = emf.createEntityManager();` 를 통해 객체를 생성할 수 있다.

나중에 스프링 부트와 결합해서 사용하면, 어노테이션을 통해서 위 과정이 생략되긴 한다.

---

<br>



## @Entity · @ID · @Column

<br>

먼저, 데이터베이스로 관리할 객체를 생성해야한다.

예시로 `Hospital` 이라는 객체를 만들고, `id`를 기본키로, `name`과 `address` 속성이 있다고 설정하겠다.

```sql
create table hospital(
id int not null primary key,
name varchar(30) not null,
address varchar(200) not null
);
```

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221031234136115.png" alt="image-20221031234136115" style="zoom:80%;" />
</p>

위와 같은 스키마를 가진, 테이블을 만들었으니 클래스를 만든다.

```java
@Entity
@Getter @Setter
public class Hospital {

    @Id
    private int id;
    
    @Column(name="name")
    private String name;
    
    private String address;

}
```

`LOMBOK` 라이브러리의 기능인 `@Getter`와 `@Setter` 를 사용하려 코드를 간결화 시켰다.

`@Entity` 어노테이션은, JPA 가 관리해야하는 객체임을 알려주는 어노테이션이다.

`@Entity(name=" ")` 으로 엔티티 이름도 지정해줄 수 있지만, 같은 클래스가 존재하는 상황이 아니면, 웬만하면 따로 지정하지 않고,

따로 지정하지 않을 시, 클래스의 이름을 그대로 사용한다.

`@Table(name=" ")`을 통해서, 데이터베이스에서 사용하는 **매핑할 테이블의 이름을 직접 지정**해줄 수도 있다. 따로 지정해주지 않을 시 엔티티 이름을 사용하여 매핑한다.

`@Id` 는 기본키에 해당하는 변수위에, 기본키 임을 표시하는 어노테이션이다.

{: .important }
> 엔티티의 경우, JPA에서 내부적으로 사용하기 위해 매개변수가 없는 기본생성자가 있어야하며, 매개변수가 있는 생성자를 추가할 시, 기본생성자를 추가해주어야 한다. 
> 
> 보통, 엔티티는 외부에서 객체로 생성되어 변경되면 좋지 않기 때문에, 기본생성자는 protected 접근 제한자로 만든다.
> 
> `@NoArgsConstructor(access = AccessLevel.PROTECTED)` 와 같은 Lombok의 어노테이션을 활용할 수 있다.

<br>

### @Column

`@Column` 을 사용하면, 실제 데이터베이스에 해당하는 속성명을 JPA에 알려준다.

따라서, 위의 경우 자바에서 사용하는 변수명이 꼭 `name`이 아니여도 매핑해준다.

<br>

```java
//등록 변경 가능 여부
@Column(name = "이름", insertable = true/false, updatable = true/false)


// 널 제약조건 & length 지정 (DDL) 
@Column(nullable = false , length = 10)
// -> 기본값 true이고, false로 할 시, NOT NULL 제약조건이 붙는다.
// -> length를 10으로 주면 VARCHAR(10)이 된다.


//직접 속성 정보 제공 (DDL)
@Column(columnDefinition = "varchar(100) default 'EMTPTY'")
// -> 컬럼 정보를 직접 줄 수 있다.
```

<br>

{: .highlight }
💡 Enum 클래스 활용 시, `@Enumrated` 어노테이션으로 명시해주고, **(EnumType.STRING)** 으로 사용하는 것이 좋다.


---
<br>

## .persist() / .find() / .remove() / .createQuery()

<br>

```java
public class JpaTest {
    public static void main(String[] args) {

        //1. Persistence 객체로 createEntityManagerFactory(persistence unit name)으로 EntityManagerFactory 생성
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("hello");

        //2. EntityManagerFactory 로 EntityManager 생성
        EntityManager em = emf.createEntityManager();

        //3. EntityManager로 EntityTransaction get
        EntityTransaction ts = em.getTransaction();

        //4. 트랜잭션 시작
        ts.begin();
        
        /*
        원하는 작업 (persist() / find() / remove() .... 등등)
         */
        
        //5. 트랜잭션 종료
        ts.commit();
        
        //6. 예외발생시 롤백
        ts.rollback();

    }
}

```

{: .warning }
> persist 과정에서 `Unknown Entity` 오류가 발생한다면, Gradle로 빌드했기 때문이고, Gradle로 빌드한 경우
> 
> persistence.xml 파일 unit-name 아래   
> 
> `<class>jpabasic.ex1hellojpa.domain.entity.Member</class>`
> 
> 위 구문을 추가해서 엔티티 위치를 명시해주어야 한다.
> 
> 순수 JPA를 사용할때, 필요한 설정이고 스프링부트 사용시에는 하지 않아도 된다.

<br>
 
전체적인 구성은 위와 같다.

`EntityManagerFactory` -> `EntityManger` -> `EntityTransaction` 순으로 생성한 뒤,

트랜잭션을 시작하고, `EntityManager` 객체를 통해서 원하는 작업을 수행하면 된다.

<br>

{: .highlight }
EntityManagerFactory는 하나만 생성해서 애플리케이션 전체에서 공유하고, EntityManager는 쓰레드간 공유되지 않는다.

<br>

### 1. .persist()

---

```java
public class JpaTest {
    public static void main(String[] args) {

        //1. Persistence 객체로 createEntityManagerFactory(persistence unit name)으로 EntityManagerFactory 생성
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("hello");

        //2. EntityManagerFactory 로 EntityManager 생성
        EntityManager em = emf.createEntityManager();

        //3. EntityManager로 EntityTransaction get
        EntityTransaction ts = em.getTransaction();

        //4. 트랜잭션 시작
        ts.begin();

        Hospital hospital = null;
        try {
            hospital = new Hospital();
            hospital.setId(1);
            hospital.setName("테스트1");
            hospital.setAddress("테스트 1 주소");

            em.persist(hospital);
            ts.commit();

        } catch (Exception e) {
            //에러 생기면 트랜잭션 시작하기 전 상황으로 되돌리기
            ts.rollback();

        } finally {
            //em이 비정상적인 오류가 생겨도 닫힐 수 있어야 함
            em.close();
        }
        emf.close();
    }
}

```

위와 같이, 매핑한 객체 맴버 변수에 데이터를 담고, `em.persist()` 해주면 데이터베이스에 등록이 된다.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221101000135150.png" alt="image-20221101000135150" style="zoom:150%;" />
</p>

데이터가 정상적으로 들어온 것을 확인할 수 있다.



### 2. .find()

---

데이터베이스의 데이터를 `em.find()` 메서드를 사용해서 찾을 수 있다.

```java
public class JpaTest {
    public static void main(String[] args) {

        //1. Persistence 객체로 createEntityManagerFactory(persistence unit name)으로 EntityManagerFactory 생성
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("hello");

        //2. EntityManagerFactory 로 EntityManager 생성
        EntityManager em = emf.createEntityManager();

        //3. EntityManager로 EntityTransaction get
        EntityTransaction ts = em.getTransaction();

        //4. 트랜잭션 시작
        ts.begin();

        Hospital hospital = null;
        try {
            Hospital findHospital = em.find(Hospital.class, 1);
            System.out.println("이름 = " + findHospital.getName());
            System.out.println("주소 = " + findHospital.getAddress());
            ts.commit();

        } catch (Exception e) {
            //에러 생기면 트랜잭션 시작하기 전 상황으로 되돌리기
            ts.rollback();

        } finally {
            //em이 비정상적인 오류가 생겨도 닫힐 수 있어야 함
            em.close();
        }
        emf.close();
    }
}
```

위와 같이, `find(찾으려는 객체 class, 찾으려는 데이터의 키 값)` 을 통해서 찾을 수 있다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221101000513606.png" alt="image-20221101000513606"  />
</p>

위와 같이, 데이터를 잘 찾아왔음을 확인할 수 있다.



### 3. .remove()

---

데이터를 삭제할 수도 있다.

삭제하려는 데이터를 먼저 찾은 뒤, 그 객체를 파라미터로 넣으면 된다.

```java
public class JpaTest {
    public static void main(String[] args) {

        //1. Persistence 객체로 createEntityManagerFactory(persistence unit name)으로 EntityManagerFactory 생성
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("hello");

        //2. EntityManagerFactory 로 EntityManager 생성
        EntityManager em = emf.createEntityManager();

        //3. EntityManager로 EntityTransaction get
        EntityTransaction ts = em.getTransaction();

        //4. 트랜잭션 시작
        ts.begin();

        Hospital hospital = null;
        try {
            Hospital findHospital = em.find(Hospital.class, 1);
            
            em.remove(findHospital);
            
            ts.commit();

        } catch (Exception e) {
            //에러 생기면 트랜잭션 시작하기 전 상황으로 되돌리기
            ts.rollback();

        } finally {
            //em이 비정상적인 오류가 생겨도 닫힐 수 있어야 함
            em.close();
        }
        emf.close();
    }
}

```

위와 같이, 객체를 찾은 뒤, `em.remove(삭제하려는 객체)` 를 통해서 삭제하면 된다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221101000719018.png" alt="image-20221101000719018" style="zoom:150%;" />
</p>

정상적으로 삭제 된 것을 확인할 수 있다.



### 4. .createQuery()

---

`createQuery()`는 쿼리문을 전달하는 메서드이다.

참고로 JPA는 데이터베이스마다 각각 다른 문법을 가졌기 때문에, 이를 호환하기 위해서 **JPQL**이라는 쿼리 문법을 갖으므로 이에 맞춰서 쿼리문을 작성해야한다.

간단한, 원하는 데이터를 범위를 지정해서 가져오는 쿼리문을 작성해서 테스트 해보겠다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221101001323562.png" alt="image-20221101001323562" style="zoom:150%;" />
</p>

먼저, 위와 같이 5개의 테스트 데이터를 등록하였다.

```java
public class JpaTest {
    public static void main(String[] args) {

        //1. Persistence 객체로 createEntityManagerFactory(persistence unit name)으로 EntityManagerFactory 생성
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("hello");

        //2. EntityManagerFactory 로 EntityManager 생성
        EntityManager em = emf.createEntityManager();

        //3. EntityManager로 EntityTransaction get
        EntityTransaction ts = em.getTransaction();

        //4. 트랜잭션 시작
        ts.begin();

        Hospital hospital = null;
        try {
            List<Hospital> results = em.createQuery("SELECT row from Hospital as row", Hospital.class).getResultList();
            
//           * 범위 지정해서 가져오고 싶은 경우            
//            List<Hospital> results = em.createQuery("SELECT row from Hospital as row", Hospital.class)
//                    .setFirstResult(2).setMaxResults(2).getResultList();
            for (Hospital result : results) {
                System.out.println(result.getName());
            }
            ts.commit();

        } catch (Exception e) {
            //에러 생기면 트랜잭션 시작하기 전 상황으로 되돌리기
            ts.rollback();

        } finally {
            //em이 비정상적인 오류가 생겨도 닫힐 수 있어야 함
            em.close();
        }
        emf.close();
    }
}

```

위와 같이 입력하면, 데이터베이스에 있는 모든 데이터를 가져올 수 있다.

`em.createQuery(JPQL구문, @Entity되어있는 객체).getResultList()` 하면, 객체가 담긴 리스트를 반환받을 수 있다.

JPQL 구문은, SQL 구문을 객체지향적으로 바꿔서 생각하면 쉽다.

위의 예시에서 사용한 JPQL 구문의 경우, Hospital 테이블의 한 레코드를 row라는 변수로서 지정하고 가져온다라고 생각하면 된다.

<br>

범위를 지정해서 데이터를 가져올 수도 있다.

`.setFirstResult()`로 가져오고 싶은 데이터의 시작 인덱스를 지정하고

`.setMaxResults()`로 가져오고 싶은 데이터의 갯수를 설정하면, 원하는 범위의 원하는 갯수의 데이터를 가져올 수 있다.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221101001958457.png" alt="image-20221101001958457" style="zoom:150%;" />
</p>


배열과 마찬가지로, index는 0부터 시작하기 때문에, first index 를 2로 지정하면 3번째 행부터 가져올 것이고,

max를 2개로 지정했기 때문에, 테스트 데이터 3,4 를 가져온 것을 확인할 수 있다.