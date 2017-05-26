# quiz_day4

## 1. custom exception 인 매치 결과가 없을 때 오류가 나는 EmptyMatchedException 정의 하시오.

```
class EmptyMatchedException(Exception)
	pass
```

## 1-1. EmptyMatchedException 의 \_\_init__ 메서드에 pattern, string 인자를 받게 하시오.

```
class EmptyMatchedException(Exception)
	def __init__(self, pattrn, string):
	self.pattern = pattern
	self.string = string
```

## 1-2. \_\_str__ 메서드에는 "일치 결과가 없습니다" 문자열을 리턴하게 하시오.

```
def __str__(self):
	return "일치 결과가 없습니다."
```

## 2. pattern, string 을 매개변수로 갖는 search함수를 정의하고, pattern찾지 못하면 EmptyMatchedException 발생하게 만드시오.

```
del search_f(pattern,string):
	m=re.search(pattern,string)
	if m:
		return m
	return	EmptyMatchedException(pattern, string)
```

## 3. try~except문을 사용하여 예외를 발생 시키시오. pattern 과 string 아래에 것을 사용하시오.

```
try:
	pattern = 'man'
	string = 'Lux, the Lady of Luminocity'
	search_f(pattern,string)
exception:
	EmptyMatchedException	
```

## 4. else 구문을 추가하여 예외가 발생하지 않았을 경우를 만들 것입니다. pattern 에 L 로 시작하는 모든 문자를 찾아오는 정규 표현 식을 만들어 pattern 변수에 할당해서 else가 실행되면 Lux, Lady, Luminocity 출력하게 만드시오.

```
try:
	pattern = r'(L[.\w].*?\b)'
	string = 'Lux, Lady of the Luminocity'
	k = search_f(pattern,string)
exception EmptyMatchedException as e:
	print(e)
else:
	print('{}'.format(k))	
```