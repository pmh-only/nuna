# nuna
(우리의 가상) 누나 언어 v0.3

### 스택
스택은 스택 번호, 값들으로 이뤄져야 합니다
값은 64비트 signed int입니다.

만약 오류가 난 경우에는 그 자리에서 오류를 알려주고 프로그램이 작동을 중단해야 합니다

### 키워드
* `눈`, `누`는 값이 1인 스택을 만듭니다 (예외, 뒤에 `.`가 있으면 `.`의 길이의 수만큼을 값으로 합니다)
* `나`는 현재 스택에 1을 곱합니다 (예외, 뒤에 `.`가 있으면 `.`의 길이의 수만큼 곱합니다)
* `주`는 현재 스택에 1을 뺍니다 (예외, 뒤에 `.`가 있으면 `.`의 길이의 수만큼 뺍니다)
* `거`는 현재 스택에 1을 더합니다 (예외, 뒤에 `.`가 있으면 `.`의 길이의 수만큼 더합니다)
* `흐`는 현재 스택을 POP합니다.
* `읏`은 앞의 스택의 값입니다. `.`대신 사용 할 수 있습니다.
* `💕`는 현재 스택 앞의 내용과 현재 스택의 내용을 합칩니다 (현재 스택 앞의 스택은 삭제 됩니다)
* `🏩`는 현재 스택 앞의 내용과 현재 스택의 내용을 뺍니다 (현재 스택 앞의 스택은 삭제 됩니다)
* `!`는 스택을 UTF-8인코딩으로 문자 출력(stdout)를 합니다.

`눈` `누`, `나`, `주`, `거`, `.`, `흐`, `읏`,`💕`, `🏩`, `!`가 아닌 다른 문자들은 문법오류입니다.

만약 키워드 뒤에 `.`가 없다면 숫자가 `0`이 아닌 `1`로 간주합니다.

#### 예제
```
눈나..나..주...나..........거나..........거....나..........거나..........거나....누........나.........🏩
누나..나..나..거나..나.....나.....거...나..나.....거나..나.....주..눈나..........나..........🏩!
```
* 출력 결과: 누나
```
누나..........누......나.....나..주......거.나..........주.거..나읏거..나읏💕주...........거
누나..........누나.....나.....나..주거..나읏주거나읏주거...나읏주거....🏩주거...........누나주..나읏나..💕눈..나..........💕!
```
* 출력 결과: 흐읏
#### 구현체
* [C++](https://github.com/hui1601/nuna-interpreter)

#### 주의
이 언어의 작가는 현재 누나가 없으며 (미래에도 없을 예정), 이 언어는 미니멀리즘을 추구합니다

##### latest release
* 3월 1일 12:50(24h)
