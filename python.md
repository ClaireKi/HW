Loop (반복문)
============
>while 문 
</br>
>while 조건:
</br>
>&nbsp&nbsp실행할 명령1
</br>
>&nbsp&nbsp실행할 명령2...

>   조건 검사 - 명령1 - 명령2 - ... - 조건검사 - 명령 1 - 명령2 - ...

>   조건이 F가 되는 그 순간까지 반복.

<pre><code>
count=0

while count < 3:
>print('횟수:', count)
>count += 1
</code></pre>



#IDLE 에서 반복문 강제 중지는 ctrl + c
    


continue와 break
================
>continue : 실행 완료 후 밑에 있는 문장으로 안 내려가고 다시 조건문으로 감

>break : 반복문 escape.

<pre><code>
count=0

while count < 10:
>count += 1
>if count < 4:
>>continue
>print('횟수:', count)
>if count == 8:
>>break
</code></pre>


Dictionary
==========
> {key1: val1, ...}


<pre><code>
my_dict = {}

print(type(my_dict))


my_dict[0] = 'a'        #key가 0, val(값)가 a

print(my_dict)

my_dict['b'] = 1        #key나 val는 문자형, 숫자형 모두 섞어서 사용 가능하다.

print(my_dict)

print(my_dict[0])       #key값을 명령하면 val가 출력됨.


del my_dict['b']        #key 삭제

print(my_dict)

my_dict[2] = 'x'

print(my_dict)

#del my_dict['x']  -> val 삭제 불가능

my_dict[0] = 'b'

print(my_dict)  # {0: 'a', 2: 'x' , 0: 'b'} 가 아님. 0: 'a'를 0: 'b'로 대체함
                #따라서 key값은 중복될 수 없다. #그럼 val는?


my_dict[4] = 'b'
print(my_dict)  #val값 중복 가능 val값을 설정해서 key값을 지우는 방법은 없을까...?

</code></pre>


dictionary의 메소드
==================

>dict.values()
</br>
>&nbsp&nbsp dictionary에서 val(값)만 뽑아오는 것
        
>dict.keys()
</br>
>&nbsp&nbsp dictionary에서 key만 뽑아오는 것
        
>dict.items()
</br>
>&nbsp&nbsp dictionary에서 key, val 동시에 뽑아오는 것
        
<pre><code>
my_dict = {}

my_dict[0] = 'a'
my_dict[1] = 'b'
my_dict[2] = 'c'
my_dict[3] = 'd'

print(my_dict)

for x in my_dict.values():
    print(x)

for y in my_dict.keys():
    print(y)

for z in my_dict.items():
    print(z)
</code></pre>

Function (함수)
===============
>정의: 반복되는 코드를 묶어서 이름을 붙여놓은 것.

>&nbsp&nbsp 1)내장함수 : 파이썬에서 기본으로 제공하는 함수 , 이름만 알면 바로 쓸 수 있음

>&nbsp&nbsp 2)모듈의 함수 : import를 해서 가져다 쓰는 함수

>&nbsp&nbsp 3)사용자 정의 함수 : 사용자가 직접 만들어 쓰는 함수

>&nbsp&nbsp&nbsp&nbsp def 함수이름(인자(=매개변수)1,...):
>&nbsp&nbsp&nbsp&nbsp&nbsp  실행할 명령1
>&nbsp&nbsp&nbsp&nbsp&nbsp  실행할 명령2
>&nbsp&nbsp&nbsp&nbsp&nbsp  ...
>&nbsp&nbsp&nbsp&nbsp&nbsp  return 결과  -> ~~이 부분은 없어도 됨.~~


>&nbsp&nbsp 사용하는 이유 : 1)계속 다시 사용 가능
>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp한 번 함수를 정의하면
>&nbsp&nbsp&nbsp&nbsp&nbsp같은 결과가 필요할 때 얼마든지 재사용 가능

>>>>>>2)코드 관리 쉬워짐
>>>>>>>a 찍어내는데 코드가 한 3줄쓰인다고 가정해보자
>>>>>>>a를 100 개 찍으려면 코드가 300줄 필요한데
>>>>>>>a 하나를 찍어내는 코드를 3줄보다 짧은 함수 하나에 정의한다면
>>>>>>>300줄보다 짧게 얼마든지 만들 수 있다.                            
                            
>>>>>>3)조립해서 사용 가능
>>>>>>>ex) 더하기 함수
>>>>>>>빼기 함수
>>>>>>>제곱 함수 ...
>>>>>>>다 모여서 뿅 계산기 함수!
'''
<pre><code>
#사용자 정의 함수인 'add' 만들기

def add(num1, num2):
    return num1 + num2

print(add(1,2))
</code></pre>

<pre><code>
#조립 예시
def add_mul (num1,num2):
    return num1 + num2 , num1*num2  #조립 가능함

print(add_mul(4,5)) #출력값이 (9,20) 이것은 소괄호 즉, 튜플로 packing된 것.
                    #그럼 unpacking도 가능하겠쥬?

my_add, my_mul = add_mul(4, 5) #umpacking

print(my_add)
print(my_mul)
</code></pre>

Module
======

>함수들을 모아놓은 파일
>import로 불러옴

>>집에서 라면 끓이려는데 가스 불 키려면 가스가 있어야겠죠?
>>가스를 우리가 직접 채취해오기가 엄청 힘들잖아요
>>그래서 우리는 도시가스에 돈을 주고 가스를 받아씁니다
>>여기서 도시가스가 바로 모듈의 개념이에요!

>>ex) random ... etc

'''
<pre><code>
#먼저 random이라는 모듈을 불러 옵시다
import random   

#그룹을 만들어 주시구요
students = ['상욜로 오빠', '현수 오빠', '봉근 오빠', '현규 오빠', '겸댕서연..ㅎ']


#choice를 써서 누가 아이스크림을 살지 정해볼게요!^^
print(random.choice(students)) 

#앞 강의에서 배운 append 메소드로 추가하고서 choice하면
#준혁오빠가 우리에게 아이스크림을 사주게 될 수도 있어요!
students.append('대표..준혁..') 


#요즘 아이스크림이 많이 비싸졌어요ㅠㅠ 두 명 뽑아서 두 명이서 사볼까요?
print(random.sample(students, 2))


#randint(a,b) a와 b사이(a,b포함)에서 임의의 정수를 뽑는 것.
print(random.randint(7,10))
</code></pre>

Object 객체
===========
>>ex) 게임 캐릭터 '용사'라는 캐릭터(객체)가 있다.
>>>용사에겐 데이터가 존재한다.
>>>-성별,레벨,HP,MP, 아이템 ...etc
>>>-행동: 때린다, 이동한다 ... etc

>>>예를 들어서
>>>x = [1, 2, 3]

>>>x라는 객체는 1, 2, 3 이라는 데이터를 가지고 있으며

>>> x.append(4) >>> x = [1, 2, 3, 4] / append라는 함수도 가지고 있는 것이다.

>>>마치 '때린다' 라는 행동을 가진 것 처럼.


PEP8
====        
>코딩 스타일 가이드
>>>코딩을 할 때는 코드가 가독성 있도록 하는 것이 좋다.
>>>because 다른 사람들과 코드를 공유하는 경우가 많기 때문에
>> https://b.luavis.kr/python/python-convention : 참고자료
        

>>일관성 있게 작성하는 것은 좋지만
>>적당히 규칙을 어겨야 할 때 (일관성을 버려야 할 때)는 버려야 한다.


Googling
========
>영어로 먼저 칠 수 있으면 아주 좋지만
>영어를 못하는 저는 한국어로 먼저 검색하고 
>여러 개를 취합해서 영어로 접근하는 게 더 편하더라구용

>코딩 계의 지식in : https://stackoverflow.com/

>오늘의 스터디 교훈:
>>코딩은 외우는 게 아니라 이해하는 것이고 모르면 검색하는 것이다.
>>무작정 머리에 넣지 말자








