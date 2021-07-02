## CSS vs JavaScript Animations

🌱: 이해 못 한 부분

<br>

**학습 목표: CSS와 JS 애니메이션의 특징과 차이점을 파악**

<br>

> 웹 애플리키에션에 애니메이션을 추가할 때 CSS의 `transition`/`animation` 등의 속성을 이용할 수 있고 JS의 `setInterval()` 등을 사용할 수 있다. 두 방식의 차이점과 특징을 알아보자

<br>

### 요약

- CSS는 `선언형` vs JS는 `명령형`
- CSS 애니메이션은 간단한 `transforms`과 `opacity` 등을 사용할 때 JS는 더 복잡하고 무거운 애니메이션에 일반적으로 사용
- CSS 애니메이션은 컴포지터 쓰레드(`compositor thread`)에서 처리하고 JS 애니메이션은 메인 쓰레드(`main thread`)에서 처리
- CSS의 경우 브라우저 호환성에 문제가 발생할 수 있으나 JS의 경우 브라우저 호환성이 더 좋다
- 애니메이션 60fps 유지하기

<br>

CSS 예시

```html
<script>
	const box = document.querySelector('.box');
    box.addEventListener('click', function() {
        box.classList.toggle('move');
    });
</script>
<styled>
.box {
    transform: translate(0, 0);
    transition: transform 500ms;
}
.box.move {
    transform: translate(100px, 100px);
}
</styled>
```

<br>

JS 예시

```js
const box = document.querySelector('.box');
box.addEventListener('click', function () {
	target.style.transform = 'translate(100px, 100px)';
  });
```

예시 코드를 실행해보면 다시 돌아가지 않고 현재 위치에 머무는 것을 확인할 수 있다



### CSS

transition과 animation 등으로 애니메이션 적용 가능

- Animation은 개별 애니메이션, 키프레임, 기간 및 반복 등을 세밀하게 조절 가능

- `@Keyframe`: 애니메이터의 모션은 특정 동작 프레임을 만든 다음 키프레임 사이사이 모든 개별 프레임을 그려 넣는 방식으로 진행

  ```css
  @keyframes animationName {
      from {
          css-styles;
      }
      to {
          css-styles;
      }
  }
  ```

<br>

#### will-change 속성

요소의 속성을 변경하려고 한다는 것을 브라우저가 미리 알도록 한다(브라우저 최적화를 돕는다)

example

```css
.box {
    will-change: transform, opacity;
}
```

단, 남용하게 되면 자원 낭비 등이 발생하여 오히려 성능에 문제가 될 수 있음

<br>

### CSS와 JS 성능 비교

`main thread`: styling, layout, painting 및 JS 실행될 때 처리하는 쓰레드

따라서 CSS 애니메이션을 사용하게 되면(`compositor thread`) 브라우저가 무거운 작업을 하고 있더라도 일반적으로 문제없이 작동할 수 있게 함

단, 레이아웃과 그리기(`paint`) 단계의 작업을 하게 되면 CSS와 JS 애니메이션 둘 다 메인 쓰레드를 이용하게 되기 때문에 주의

<br>

### 참고 자료

[Google developers, CSS와 JavaScript Animation](https://developers.google.com/web/fundamentals/design-and-ux/animations/css-vs-javascript?hl=ko)

[Google developers, Animations and Performance](https://developers.google.com/web/fundamentals/design-and-ux/animations/animations-and-performance#css-vs-javascript-performance)

[CSS Animation 어떻게 사용하고 계신가요?](https://brunch.co.kr/@99-life/2)

[CSS 애니메이션(Animation), 키프레임(keyframes)](https://webclub.tistory.com/621)

