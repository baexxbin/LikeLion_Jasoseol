# LikeLion_Jasoseol
### OT

1. 우리가 만들 서비스
* 자기소개서 관리 서비스

2. 집중할 포인트
* django답게 코딩하기!
    - 생산성이 높다!
    - 장고기능 최대한 활용하기!

* 데이터, 데이터베이스, 모델에 집중!
    - 데이터를 다룬다는 개념 상기하면서 듣기!
    - html,css기능 최소한으로 배움

3. Django가 만들어놓은 기능
    - 숨겨진 만들어진 기능들 찾아보기
        + Django 공식 깃허브 : https://github.com/django
        + Django 공식 문서 : https://docs.djangoproject.com/ko/3.0/
    - render 함수 알아보기
    ````
    def render(request, template_name, context=None, content_type=None, status=None, using=None):
    """
    Return a HttpResponse whose content is filled with the result of calling
    django.template.loader.render_to_string() with the passed arguments.
    """
    content = loader.render_to_string(template_name, context, request, using=using)
    return HttpResponse(content, content_type, status)
    ````
        + django.shortcut 에 속해있음
        + 첫번째 인자: request // 두번째 인자:templete name // 세번째 인자: context=None
        + reuturn을 HttpResponse라는 함수에 content를 담아서 보냄
        + HttpResponse : 원초적인 응답, 반응
        + context들이 담겨진 templete을 받아와서 단순히 http응답을 해줌
