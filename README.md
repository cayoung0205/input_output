### 입력과 출력

#### print(): 문자열, 숫자 출력

> `sep = 문자열` : 두 문자열 사이의 구분하는 값을 설정
>
> `+` : 콤마 대신 연결
>
> `,` : 공백 
>
> 콤마와 더하기는 동시에 사용 가능
>
> `\n`  : 줄 바꿈 , 연속사용 가능
>
> `end = 문자열` : 라인 끝의`\n`을 대신해서 문자열 입력

### 형식 지정 출력

```python
<변수A> = '<내용>''
print('%s 내용' % 변수A)  ## %s 자리에 변수A 할당된 문자열 출력

# %s : string
# %i, %d: int
# %f, %F: float 
```

### `string.format()`

```python
<변수 A> = "A"
<변수 B> = "B"
<변수 C> = "C"

print("내용: {0}",format(변수A)) ## 지정 위치 {0}에 <변수 A> 값 출력
                               ## 지정 위치 변경 시 변겨되어 출력
                               ## 순차적으로 출력 시 {} ## N 값 없이 작성 
```

### `숫자열.format()`

```python
a = 0.123456789012345678
pritn("{0:.2f}").fomat(a))  ## 소수점 둘째 자리 출력
```

### input()

- input() 함수로 부터 입력 받은 데이터를 출력
- 숫자 입력 --------> 문자열 출력 `연산 전 변환 필수`

### Read 읽기

1. HDD 데이터 파일 Memory 올리기
2. 읽기 방식(Readline 등)

### Write 쓰기

1. Memory data



- 읽기 : `open()` `read()` `close()`
- 쓰기 : `open()` `write()` `close()`

> 파일은 항상 오픈하고 클로즈 해야함.
>
> 'w' == 'wt'



```python
f = open('file_name', 'mode')  # f = open ('filename')도 가능
data = f.mode()
f.close ## 항상 닫아주기
```



#### 반복문을 이용해 한 줄 씩 쓰기

```python
f = open('file_name', 'w') ## 쓰기모드로 열기   
for <반복 변수> in <반복 범위>: ## 반복 범위를 반복 변수가 반복
	<new_file> = "내용"  ## 내용 생성
    f,write(new_file)   ## 내용 저장   
f.close()               ## 파일 닫기
```



#### `readline()` :한 줄 씩 읽기 

```python
f = open('file_name')  ## 읽기 모드로 열기 
line1 = readline()     ## 한 줄씩 문자열을 읽기   ---> 차이
while line:            ## line의 공백 검사 후 반복 여부 결정 
    print(line)        ## 한 줄 출력
    line = f.readline() ## 한 줄 읽기
f.close()             ## 파일 닫기
```

#### `readlines()`: 한 줄 씩 읽기

```python
f = open('file_name') ## 읽기모드 열기
<변수> = f.eadlines()  ## 파일 전체 읽기(리스트로 반환)       ---> 차이
f.close()             ## 닫기
for <반복 변수> in <반복 범위>:## 리스트의 <반복 범위>를 지정
	print(line)       ## 리스트 항목을 출력
```

#### `with` 문 활용

````python
with open('file_name', 'mode') as f: 
	<코드 블럭>
	
# 코드 블럭의 코드가 끝나면 open()으로 열린 파일 객체 자동으로 close()
````

