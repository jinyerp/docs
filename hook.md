# Hook 개념
---
visitor 패턴의 개념을 응용하여 이벤트를 연결하는 방법입니다.

후크를 통하여 컨덴츠를 특정 영역에 삽입을 할 수 있습니다.

특정 사항에서, 특정 작업을 수행합니다.

후크의 동작은 크게 2가지로 구분됩니다.
* action~ : 특정 동작을 이르키는 이벤트 트리거
* display~ : 프론트,admin에 출력되는 무언가...


```php
$this->registerHook('displayHeader');
```
이렇게 등록된 후크는, 모듈의 hook~ 시작되는 메소드와 매칭하여 호출됩니다.

정의된 후크 동작은 호출되는 곳에서 전달되는 매개변수 배열을 하나 가지고 있습니다.

```php
public function hookDisplayHeader(array $params)
{

}
```

후크 호출하기
컨트럴러 내에서 
```php
Hook::exec($hook_name, $hook_args = []);
```

후크의 기본 호출 :
```
{hook h='displayLeftColumn'}
```
특정 모듈에 대한 후크 호출 :

```
{hook h='displayLeftColumn' mod='blockcart'}
```



