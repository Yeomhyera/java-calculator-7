## 🧮 문자열 계산기
 
문자열 1줄을 입력 받아 포함되어 있는 모든 숫자들의 합을 출력한다.

---

#### [INPUT]

- 구분자 + 숫자 조합으로 이뤄진 문자열이다.
- ex
    - `""` 
    - `"1,2"` 
    - `"1,2,3"` 
    - `"1,2:3"`

#### [OUTPUT]
- 공백 없이 숫자합 한 줄에 출력한다.
- ex)
    - `""` → **0**
    - `"1,2"` → **3**
    - `"1,2,3"` → **6**
    - `"1,2:3"` → **6**


---

#### 1. 입력 처리

- 사용자가 형식에 맞지 않은 입력을 보낼 경우 `IllegalArgumentException` 오류를 반환한다.
  - 1. 숫자가 아닐 경우
  - 2. 양의 정수가 아닐 경우

---

#### 2. 구분자 추출

- 커스텀 구분자를 사용할 수 있도록 입력 시 받아낸다.
- 커스텀 구분자 : 문자열 맨 앞에서 `"//"`로 시작하여 `"\n"` 사이에 위치한 문자들을 사용한다.

- ex)
    - `"//;\n1;2;3"` → **6** (`;`이 구분자)
    - `"//|\n10|20|30"` → **60** (`|`이 구분자)

---

#### 3. 숫자 추출

- 구분자 사이에 포함된 모든 숫자를 추출한다.
