# LikeLion_Jasoseol
### User #1

<오늘 할 것>
* User모델
* url 상속
* 회원가입 구현

*실습*
* 하위 앱 생성시 url상속하기
```
from django.urls import path, include
path('', include('accounts.urls')),
```