#⚡️FastAPI

python3.6 이상으로 API를 빌드하기 위한 고성능 모던 프레임워크

### 특징(Key features)

---

1. Fast : 높은 퍼포먼스
2. Fast to coce : 빠른 개발 속도
3. Fewer bugs
4. Intuitive
5. Easy : 낮은 러닝커브
6. Short : 코드 반복을 최소화
7. Robust : 자동으로 문서를 생성
8. Standard-based : API를 위한 open standard를 기준으로 함

## ⚙️설치

### 개발환경(Requirements)

---

- python 3.6+

### 예제 파일

---

1. 패키지 설치

```bash
$ pip install fastapi
$ pip install uvicorn
```

2. [main.py](http://main.py) 작성

```python
from typing import Optional
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
	return { "Hello" : "World" }

@app.get("/items/{item_id}")
def read_item(item_id: int, q: Optional[str] = None) :
    return {"item_id" : item_id, "q" : q}
```

3. 실행

```bash
$ uvicorn main:app --reload
```

[**main**.py](http://main.py) 모듈안에서 **app** = FastAPI() 객체를 실행한다.

**—reload** 옵션을 추가하면 파일 내용이 바뀔 때바다 서버가 restart 된다.

url : /

<img width="912" alt="Screen Shot 2021-03-22 at 3 59 32 AM" src="https://user-images.githubusercontent.com/30452963/111917691-c186eb80-8ac4-11eb-8026-6428b70e9a4b.png">

url : /items/{item_id}

<img width="912" alt="Screen Shot 2021-03-22 at 3 59 47 AM" src="https://user-images.githubusercontent.com/30452963/111917695-c64b9f80-8ac4-11eb-8438-2b93b37158b9.png">

url : /docs

<img width="912" alt="Screen Shot 2021-03-22 at 3 59 59 AM" src="https://user-images.githubusercontent.com/30452963/111917697-c77ccc80-8ac4-11eb-8174-d8837356ede7.png">