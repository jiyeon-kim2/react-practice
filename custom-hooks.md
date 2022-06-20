# 커스텀 훅 만들기

## 목적

- 리액트 훅 학습하기
- 커스텀 훅에 대한 규칙 학습하기
- 다양한 유형의 커스텀 훅 만들어보기

## 과제 1

### [ 요약 ]

값이 변경되는 시점에만 콘솔이 출력되는 useWatch 훅을 만드세요

### [ 설명 ]

다음 코드에서 count 값은 버튼 클릭을 통해서만 변경되지만 실제 콘솔 출력은 렌더링 때 마다 출력됩니다.

```js
const [count, setCount] = useState( 0 );
const [timer, setTimer] = useState( 0 );

useEffect( () => {
  setInterval( () => {
    setTimer( value => value + 1 );
  }, 100 );
}, [] );

console.log( count );

return <button onClick={ () => setCount( count => count + 1 ) }>Add Count</button>
```

다음과 같이 사용해서 실제 count 값이 변경될 때에만 콘솔이 출력되도록 useWatch 훅을 만들어보세요.
```js
const [count, setCount] = useState( 0 );
const [timer, setTimer] = useState( 0 );

useEffect( () => {
// 위와 같으므로 생략
}, [] );

useWatch( count );

return <button onClick={ () => setCount( count => count + 1 ) }>Add Count</button>
```

## 과제 2

### [ 요약 ]

useEffect 시점에 자유롭게 async 함수를 쓸 수 있는 useAsyncEffect 훅을 만드세요.

### [ 설명 ]

useEffect 내에서 async 함수를 쓰려면 다음과 같은 형태가 되어 번거롭습니다.

```js
useEffect( () => {
  async function exec() {
    await sleep( 1 );
    console.log( 'exec!' );
  }
  exec();
}, [] );
```
다음과 같이 사용할 수 있도록 useAsyncEffect 훅을 만들어보세요.
```js
useAsyncEffect( async function() {
  await sleep( 1 );
  console.log( 'exec!' );
} );
```

## 과제 3

### [ 요약 ]

useNavigate 훅을 만드세요

### [ 설명 ]

다음과 같이 동작하는 useNavigate 훅을 만들어보세요.

```js
const navigate = useNavigate();
navigate( '/home' ); // /home 주소로 이동
navigate( -1 ); // 뒤로 이동
navigate( 1 ); // 앞으로 이동
```

** 주의 : react-router-dom 에 동일한 이름의 훅이 있으니 react-router-dom 이 없는 프로젝트에서 만들어보세요.
** window.location, window.history 를 이용합시다.
