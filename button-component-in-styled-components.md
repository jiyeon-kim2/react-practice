# 스타일드 컴포넌트로 버튼 컴포넌트 만들기

## 목적

스타일드 컴포넌트의 props 활용법을 학습하기

## 요약

부트스트랩의 Button 컴포넌트의 일부 스펙을 스타일드 컴포넌트로 제작합니다.

## 설명

부트스트랩의 가장 대표적인 컴포넌트는 Button 입니다.  
https://getbootstrap.com/docs/5.2/components/buttons/  

스타일드 컴포넌트를 이용해서 부트스트랩의 버튼 컴포넌트를 만들어 봅시다.

```js
// components/atoms/Button.tsx // or jsx
const Button = styled.button`
  // 구현
`
export default Button;
```

```js
// App.tsx // or jsx
import Button from './components/atoms/Button';

<Button color="primary">
  Click Me
</Button>
```

리액트에 적용을 해야 하는 만큼 class name 나열로 사용하는 부트스트랩과 최종 코드 면에서 차이가 발생할 수 밖에 없습니다.  
이 때 참조할 수 있는 것으로 부트스트랩의 리액트 포팅인 ReactStrap 에서 리액트로 사용할 경우의 props 스펙을 볼 수 있습니다.  
https://reactstrap.github.io/?path=/docs/components-button--button
참조하여 구현 하시기 바랍니다.
