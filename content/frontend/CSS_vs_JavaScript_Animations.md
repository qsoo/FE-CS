## CSS vs JavaScript Animations

π±: μ΄ν΄ λͺ» ν λΆλΆ

<br>

**νμ΅ λͺ©ν: CSSμ JS μ λλ©μ΄μμ νΉμ§κ³Ό μ°¨μ΄μ μ νμ**

<br>

> μΉ μ νλ¦¬ν€μμμ μ λλ©μ΄μμ μΆκ°ν  λ CSSμ `transition`/`animation` λ±μ μμ±μ μ΄μ©ν  μ μκ³  JSμ `setInterval()` λ±μ μ¬μ©ν  μ μλ€. λ λ°©μμ μ°¨μ΄μ κ³Ό νΉμ§μ μμλ³΄μ

<br>

### μμ½

- CSSλ `μ μΈν` vs JSλ `λͺλ Ήν`
- CSS μ λλ©μ΄μμ κ°λ¨ν `transforms`κ³Ό `opacity` λ±μ μ¬μ©ν  λ JSλ λ λ³΅μ‘νκ³  λ¬΄κ±°μ΄ μ λλ©μ΄μμ μΌλ°μ μΌλ‘ μ¬μ©
- CSS μ λλ©μ΄μμ μ»΄ν¬μ§ν° μ°λ λ(`compositor thread`)μμ μ²λ¦¬νκ³  JS μ λλ©μ΄μμ λ©μΈ μ°λ λ(`main thread`)μμ μ²λ¦¬
- CSSμ κ²½μ° λΈλΌμ°μ  νΈνμ±μ λ¬Έμ κ° λ°μν  μ μμΌλ JSμ κ²½μ° λΈλΌμ°μ  νΈνμ±μ΄ λ μ’λ€
- μ λλ©μ΄μ 60fps μ μ§νκΈ°

<br>

CSS μμ

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

JS μμ

```js
const box = document.querySelector('.box');
box.addEventListener('click', function () {
	target.style.transform = 'translate(100px, 100px)';
  });
```

μμ μ½λλ₯Ό μ€νν΄λ³΄λ©΄ λ€μ λμκ°μ§ μκ³  νμ¬ μμΉμ λ¨Έλ¬΄λ κ²μ νμΈν  μ μλ€



### CSS

transitionκ³Ό animation λ±μΌλ‘ μ λλ©μ΄μ μ μ© κ°λ₯

- Animationμ κ°λ³ μ λλ©μ΄μ, ν€νλ μ, κΈ°κ° λ° λ°λ³΅ λ±μ μΈλ°νκ² μ‘°μ  κ°λ₯

- `@Keyframe`: μ λλ©μ΄ν°μ λͺ¨μμ νΉμ  λμ νλ μμ λ§λ  λ€μ ν€νλ μ μ¬μ΄μ¬μ΄ λͺ¨λ  κ°λ³ νλ μμ κ·Έλ € λ£λ λ°©μμΌλ‘ μ§ν

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

#### will-change μμ±

μμμ μμ±μ λ³κ²½νλ €κ³  νλ€λ κ²μ λΈλΌμ°μ κ° λ―Έλ¦¬ μλλ‘ νλ€(λΈλΌμ°μ  μ΅μ νλ₯Ό λλλ€)

example

```css
.box {
    will-change: transform, opacity;
}
```

λ¨, λ¨μ©νκ² λλ©΄ μμ λ­λΉ λ±μ΄ λ°μνμ¬ μ€νλ € μ±λ₯μ λ¬Έμ κ° λ  μ μμ

<br>

### CSSμ JS μ±λ₯ λΉκ΅

`main thread`: styling, layout, painting λ° JS μ€νλ  λ μ²λ¦¬νλ μ°λ λ

λ°λΌμ CSS μ λλ©μ΄μμ μ¬μ©νκ² λλ©΄(`compositor thread`) λΈλΌμ°μ κ° λ¬΄κ±°μ΄ μμμ νκ³  μλλΌλ μΌλ°μ μΌλ‘ λ¬Έμ μμ΄ μλν  μ μκ² ν¨

λ¨, λ μ΄μμκ³Ό κ·Έλ¦¬κΈ°(`paint`) λ¨κ³μ μμμ νκ² λλ©΄ CSSμ JS μ λλ©μ΄μ λ λ€ λ©μΈ μ°λ λλ₯Ό μ΄μ©νκ² λκΈ° λλ¬Έμ μ£Όμ

<br>

### μ°Έκ³  μλ£

[Google developers, CSSμ JavaScript Animation](https://developers.google.com/web/fundamentals/design-and-ux/animations/css-vs-javascript?hl=ko)

[Google developers, Animations and Performance](https://developers.google.com/web/fundamentals/design-and-ux/animations/animations-and-performance#css-vs-javascript-performance)

[CSS Animation μ΄λ»κ² μ¬μ©νκ³  κ³μ κ°μ?](https://brunch.co.kr/@99-life/2)

[CSS μ λλ©μ΄μ(Animation), ν€νλ μ(keyframes)](https://webclub.tistory.com/621)

