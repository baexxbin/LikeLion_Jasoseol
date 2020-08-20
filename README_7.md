# LikeLion_Jasoseol
### User #2

<오늘 할 것>
* Foreign Key
    => 1:N 연결관계 가능        
    => 모델끼리의 관계 가능

* 작성자 추가하기
* Permission
* Decorator
* filter

*실습*
* 수정삭제 권한
1. detail.html 페이지에서 if문으로 권한주기     
    => url로 조종하면 뚫림      
    => 함수내에서 permision걸어주기!


2. views.py로 함수내에서 제한걸기
```
 my_jss = Jasoseol.objects.get(pk=jss_id)
    if request.user == my_jss.author:
        my_jss.delete()
        return redirect('index')

    raise PermissionDenied
```

3. .objects
* 모델.objects.all()
* 모델.objects.get()
* 모델.objects.filter()