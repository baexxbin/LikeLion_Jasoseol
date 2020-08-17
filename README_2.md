# LikeLion_Jasoseol
### 모델과 데이터베이스

<오늘 할 내용>
1. Model & Databse
* 장고프로젝트와 데이터베이스는 별도의 공간
* 데이터베이스와의 상호작용중 SQL 필요 X
* ORL사용
* 모델
    - 데이터를 담는 틀, 저장공간
    - 장고project 내부에서 모델정의-> 데이터베이스에게 알려줌 -> 모델에 맞춰 데이터베이스가 저장공간,틀 생성
    - 하나하나의 데이터 : object
    - 하나의 목록 : colum
    ````
    장고프로젝트 ===> 데이터베이스          
        "어떤 object CRUD해줘"      
    ````
    - 모델을 짰을때 DB에 알리기
        ````
        $python manage.py makemigratons     
        모델을 파이썬 형식으로 짬       
        DB가 알아들을 수 있도록 번역파일 생성       
        makemigratons안에 번역파일 차곡차곡 생성
        ````
        ````
        $python manage.py migrate   
        번역과정 거친후 실행하는 명령어     
        DB가 migratons파일(번역파일)을 참조     
        원하는데로 DB구성하라고 DB한테 이야기
        ````

2. 데이터베이스 살펴보기
* DB종류
    - SQLite3
    - MySQL
    - PostgreSQL
    - ORACLE

* 장고 기본적으로 SQLite3에 연결
    - 외부DB연결할 상황생김
        + settings.py에 연결을 원하는 DB정보 쓰고 연동

3. 모델을 데이터베이스에 반영하기
* 실습
    * admin페이지 이용해 만들어진 자소설모델의 데이터추가
    * 기본환경구성        

    1. $ python manage.py migrate      
    -> db.sqlite3생성됨     
    ````
     Apply all migrations: admin, auth, contenttypes, sessions
     -> settings.py 안의 INSTALLED_APPS(기본적으로 장고에서 만들어 놓은 애들) 적용됨
    ````
    2. main (app) 만들기
    ```
    $ python manage.py startapp main
    ``` 
    * 앱 만든 순간 항상 프로젝트에 연결 시켜주기
    settings.py - INSTALLED_APPS -['main',]     

    * main파일 안에 models.py 생성됨
        - 자소설모델 만들기
            - 클래스로 만듦
        ```
         updated_at = models.DateTimeField(auto_now=True)       
         어떤 자기소개서가 생성이되거나 업데이트가 될 때 그시간과 날짜를 자동으로 updated_at에 저장
         ```
    * makemigrations를 하는 시기
        - DB에 반영할 모델이 새로 추가 되었을때
        - 변경사항이 생겼을때 함
        => makemigrations 파일안에 번역파일 차곡차곡 쌓임
    * migrate
        - makemigrations(번역파일)을 기반으로 db.sqlite3에 번역파일을 토대로 자소설을 연결해줌
    ==> 데이터 베이스에 모델 반영

3. 우리가 만든 자소설모델 admin에서 보기
    - 이미 main-models.py에 모델 만들어놓음
    - main-admin.py에 만든 모델 열결시켜주기
        ```
        from .models import Jasoseol   
        ```
        ```             
        admin.site.register(Jasoseol)       
        ```
페이지에서 자소서가 잘 등록 됨!

