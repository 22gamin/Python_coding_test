-선택정렬과 기본 정렬 라이브러리의 수행시간비교

```
from random import randint
import time

#배열에 10,000개의 정수를 삽입
array=[]
for _ in range(10000):
    array.append(randint(1,100))  #1부터 100사이의 랜덤한 정수

#선택 정렬 프로그램 성능 측정
start_time=time.time()

#선택 정렬 프로그램 소스코드
for i in range(len(array)):
    min_index=i  #가장 작은 원소의 인덱스
    for j in range(i+1,len(array)):
        if array[min_index] > array[j]:
            min_index=j
    array[i],array[min_index]=array[min_index], array[i] #스와프

end_time = time.time() #측정종료
print("선택 정렬 성능 측정: ", end_time-start_time) #수행시간 출력

#배열을 다시 무작위 데이터로 초기화
array=[]
for _ in range(10000):
    array.append(randint(1,100))  #1부터 100 사이의 랜덤한 정수

#기본 정렬 라이브러리 성능 측정
start_time=time.time()

#기본 정렬 라이브러리 사용
array.sort()

end_time = time.time() #측정 종료
print("기본 정렬 라이브러리 성능 측정: ",end_time-start_time) #수행 시간 출력
```

# 그리디알고리즘
- 큰 수의 법칙

```
#N,M,K입력
N,M,K= map(int,input().split())

#N,M,K조건
if K>=M:
    print("다시 입력해주세요.")
    N,M,K= map(int,input().split())

if N<2 or M<1 or K<1:
    print("다시 입력해주세요.")
    N,M,K= map(int,input().split())

#배열에 넣기
array=[]
array = input().split()

#내림차순 정렬
array.sort(reverse=True)

sum=0
count=0

for i in range(M):
    if count == K:
        sum += int(array[1]) #두번째로 큰 수 넣기
        count=0
    else: 
        sum+=int(array[0])   #가장 큰 수 더하기
        count +=1
        
print(sum)
```
 가장 큰 수와 두번째로 큰 수만 쓰이는 사실을 알고 있었지만 내가 생각하지 못한 경우의 수가 나올거 같아 불안했다.
 그래서 array[0]과 array[1]이라는 특정한 표현을 쓰지 않고 코드를 작성하려했다. 그 결과 멀리 돌아갔고 코드의 방향을 잃었다.
 결론적으로는 내 아이디어를 믿지 못해 발생한 문제였다. 다음에는 더 자신감을 가지고 문제를 풀 것이다.
