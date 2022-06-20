# Promisification

## 목적

- Promise 에 대해서 학습하기
- Promise 기반이 아닌 비동기 작업을 Promise 화 하는 방법 학습하기

## 과제 1

sleep() 함수 작성하기

### [ 요약 ]

setTimeout 을 Promisification 한 sleep() 함수를 만듭니다.  
참고 : https://javascript.info/promisify

### [ 설명 ]

고전 프로그래밍에는 다음과 같은 sleep() 함수가 있습니다.
```
print("*");
sleep( 1 ); # 1초 대기 후 이후 코드 실행
print("**");
```

자바스크립트에서는 setTimeout을 이용해 구현이 가능하나 다음과 같이 처리되어야 합니다.
```
console.log('*');
setTimeout( () => {
  console.log('**');
}, 1000 );
```
이를 Promise로 구현해 sleep() 함수를 선언한 다음 다음 다음과 같이 실행할 수 있도록 만드세요.
```
async function exec() {
  console.log('*');
  await sleep(1);
  console.log('**');
}
exec();
```

## 과제 2

indexedDB CRUD 라이브러리 만들기

참고 : https://developer.mozilla.org/ko/docs/Web/API/IndexedDB_API/Using_IndexedDB

### [ 설명 ]

localStorage, sessionStorage의 경우 동기로 증시 실행 결과가 반영되나, indexedDB 의 경우 비동기로 이벤트를 통해 결과를 받아야 합니다.  
이 비동기 이벤트를 Promisify 해서 await 혹은 then() 을 이용해 처리할 수 있도록 라이브러리를 작성합니다.  
보통 이런 작업은 쿼리 빌더, 혹은 ORM 같은 형태로 구현이 되나 그렇게 고도화된 내용을 전부 포함할 필요는 없고 데이터의 생성/조회/수정/삭제 에 대한 4가지 기능만 간단히 테스트 할 수 있도록 작성하세요.
