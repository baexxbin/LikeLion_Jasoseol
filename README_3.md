# LikeLion_Jasoseol
### ModelForm

<오늘 할 것>
1. ModelForm을 활용한 create
* 모델폼이란?
    * 모델에 대응하는 html폼을 만들어줌
    * 데이터생성, 업데이트 간편

*실습*        
    * main-forms.py 생성

    * 장고에서 forms 가져오기      
    
    ```
    from django import forms
    from .models import Jasoseol
    ```
         
    * 모델폼 class로 만들기       
    
    ```
    class JssForm(forms.ModelForm):

        class Meta:
            model = Jasoseol // 어떤html과 대응될지 모델적어줌      
            fields = ('title', 'content',) // 모델안에서 어떤것들만 폼을 만들지     
    ```

*오류*
```
name 'OS' is not defined        
=> os.path.join을 Path로 바꾸기
```    

*  display: flex;
```
해당 클래스 안에있는 자식요소들을 컨트롤 할 수 있다.
```

2. ModelForm 속성 제어
 * {% csrf_token %}      
    django에서 POST 관련 요청 해줬을 때     
    csrf공격 막아줄 수 있는 보안토큰 

* redirect('index')함수
    render => 데이터넘겨줌      
    redirect => 단순히 index페이지로 보내주기만 하면됨        

3. 기본 레이아웃 구성
* djaingo 템플릿 필터
    년 월 일 이쁘게하기

* 모델폼 커스텀
