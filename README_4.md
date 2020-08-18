# LikeLion_Jasoseol
### PrimaryKey

<오늘 할 것>
* Primary Key [PK]
    * 오브젝트를 식별할 수 있는 값
    * 중복될 수 없는 단일 값
    * 오브젝트가 꼭가져야 함        
    (정해주지 않으면 자동으로 id가 기본키가 됨)     
    * 따로 PK를 지정하고싶다면 필드에서 지정
    * object CRUD해줘! 할때 PK데리고 가기

    *실습*
    * urls.py => 함수를 띄어주는 역할


    *오류*
    ```
    [Errno 2] No such file or directory (manage.py)
    ```
    => manage.py가 있는 디렉토리로 이동한 후 서버돌리기, cd JssProject

    ```
    from main.views import index, create, detail
    ```
    => templates에 만든 html들은 urls.py에서 import하는거 빼먹지않기

    veiws.py에서 파이썬 줄 잘 맞추기!!