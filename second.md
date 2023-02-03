## 숫자 카드 게임

```
#행의 개수 N과 열의 개수 M이 입력
N,M=map(int,input().split())

smallest=[]

#숫자 입력
for i in range(N):
    number=list(map(int,input().split()))
    small=number[0]
    for j in number:
        if j < small:
            small=j
    smallest.append(small)

big=smallest[0]
for k in smallest:
    if k > big:
        big = k

print(big)

# 행 하나를 입력한 후 그것을 리스트에 넣어 바로 가장 작은 수를 찾는다. 그렇게 모든 행을 입력한 뒤, 각 행 중 가장 작은 수를
# 또 다른 리스트(smallest)에 넣는다. 각 행 중 가장 작은 수만 모아놓은 리스트에서 가장 큰 수를 찾는다. 
```

-답안 예시
```
#N, M을 공백으로 구분하여 입력받기
n,m=map(int,input().split())

result=0
#한 줄씩 입력받아 확인
for i in range(n):
    data=list(map(int,input().split()))
    #현재 줄에서 '가장 작은 수' 찾기
    min_value=min(data)
    #'가장 작은 수'들 중에서 가장 큰 수 찾기
    result=max(result,min_value)

print(result)
```

> min함수
- min(x)함수는 최소값을 찾아서 반환하는 함수이다.
> max함수 
- 반대로 최대값을 찾아서 반환하는 함수이다.


## 1이 될 때까지
```
# 어떤 수 n과 나누어지는 수 k 입력
n,k =map(int,input().split())

#n은 k보다 항상 크거나 같다.
if n < k:
    print("다시 입력해주세요!")
    n,k =map(int,input().split())

count=0

while(1):
    if n%k==0:
        n= n/k
        count +=1
    else:
        n=n-1
        count+=1
    if n==1:
        break

print(count)
```

- 답안 예시

```
# n,k를 공백으로 구분하여 입력받기
n,k = map(int,input().split())
result=0

while True:
    #(n == k로 나누어떨어지는 수)가 될 때까지 1씩 빼기
    target = (n//k)*k  #나머지를 없앰
    result += (n-target)
    n = target
    #n이 k보다 작을 때(더 이상 나눌 수 없을 때) 반복문 탈출
    if n<k:
        break
    # k로 나누기
    result +=1
    n//=k

#마지막으로 남은 수에 대하여 1씩 빼기
result += (n-1)
print(result)
```
