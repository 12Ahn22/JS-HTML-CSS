## ๐12_glassmorphism

- ์ฐธ๊ณ  ์์์์๋ js ์ ๋๋ฉ์ด์ ๋ก์ง์ด ์์ง๋ง ์ถ๊ฐ๋ก ๊ตฌํ
- ๋งํฌ์ ์์ 
- BEM ๋ฐฉ๋ฒ ์ ์ฉ

---

[์ฐธ๊ณ  ๋งํฌ](https://www.youtube.com/watch?v=Y1CXUfZOZ40)

![12๊ธ๋์ค๋ชจํผ์ฆ20210906_205717](https://user-images.githubusercontent.com/44540726/132214066-42faea9c-c13a-4e69-bbf5-7ae64dd2b5ca.gif)

## ๊ณต๋ถ

### `backdrop-filter`

์์ ๋ค ์์ญ์ ํ๋ฆ์ด๋ ์์ ์ํํธ ๋ฑ ๊ทธ๋ํฝ ํจ๊ณผ๋ฅผ ์ ์ฉํ๋ CSS ์์ฑ

์์ ๋ค์ ์ ์ฉํ๊ธฐ ๋๋ฌธ์ ์ ์์๋ ์ ์์์ ๋ฐฐ๊ฒฝ์ ์ ์ด๋ ๋ฐํฌ๋ชํ๊ฒ ์ค์ ํด์ผํ๋ค.

```css
/* ์์ ๋ฐฐ๊ฒฝ์ ํฌ๋ชํ๊ฒ ์ค์  */
background: rgba(255, 255, 255, 0.1);
/* backdrop-filter - ์์ ๋ค ์์ญ์ ํ๋ฆผ์ด๋ ์์ ์ํํธ ๋ฑ ๊ทธ๋ํฝ ํจ๊ณผ๋ฅผ ์ ์ฉํ๋ ์์ฑ, ์์ ๋ค์ ์ ์ฉํ๊ธฐ ๋๋ฌธ์ ์ ์์๋ ์์์ ๋ฐฐ๊ฒฝ์ ์ ์ด๋ ๋ฐํฌ๋ชํ๊ฒ๋ ์ค์ ํด์ผํ๋ค.*/
backdrop-filter: blur(15px);
```

### `transform-origin`

transform์ ๊ธฐ์ค์ ์ ์ฎ๊ฒจ์ค๋ค.

### `์์.getBoundingClientRect()`

ํด๋น ์์์ DOM ์์น/ํฌ๊ธฐ ์ ๋ณด๋ฅผ ์ ๊ณตํด์ค๋ค. [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect)

- ๋ทฐํฌํธ ๊ธฐ์ค์ผ๋ก Rect ์์น ์ ๋ณด ์ ๊ณต

- ํด๋น ์์์ width์ height ์ ๋ณด ์ ๊ณต

  ```js
  const rect = e.target.getBoundingClientRect();
  ```

### `perspective`

ํด๋น ์์๋ฅผ 3์ฐจ์์ผ๋ก ๋ง๋ ๋ค.

- ์ฆ, (x,y,z) ์ธ ๊ฐ์ง ์ขํ๋ฅผ ๊ฐ์ง๊ฒ ๋๋ค.
- `perspective`๋ฅผ ์ฌ์ฉํด ๋ง์ฐ์ค ์ขํ์ ๋ฐ๋ผ ์นด๋๊ฐ ์์ง์ด๋๋ก ๋ง๋ค ์ ์๋ค.

  ```js
  // ํด๋น ์นด๋์ ์ขํ์ ๋ง์ฐ์ค ์์น๋ฅผ ์ฌ์ฉํด ์์ง์ด๋ css ๊ตฌํํ๊ธฐ
  const card = document.querySelector('#card');
  card.addEventListener('mousemove', (e) => {
    const rect = e.target.getBoundingClientRect();
    const x =
      e.offsetX <= rect.width / 2
        ? (rect.width / 2 - e.offsetX) / 10
        : (rect.width / 2 - e.offsetX) / 10;
    const y =
      e.offsetY <= rect.height / 2
        ? (rect.height / 2 - e.offsetY) / 10
        : (rect.height / 2 - e.offsetY) / 10;
    card.style.transform = `perspective(1000px) rotateX(${y}deg) rotateY(${-x}deg) `;
  });
  ```

  card์ `mousemove`์ด๋ฒคํธ๊ฐ ์ผ์ด๋ฌ์ ๊ฒฝ์ฐ

  - ํด๋น ์์์ ์์ ํฌ๊ธฐ๋ฅผ ๊ณ์ฐ

    ```js
    const rect = e.target.getBoundingClientRect();
    ```

  - ๋ง์ฐ์ค์ ์์น์ ๋ฐ๋ฅธ rotate ๊ฐ๋ ์ค์ ํ๊ธฐ

    ```js
    const x =
      e.offsetX <= rect.width / 2
        ? (rect.width / 2 - e.offsetX) / 10
        : (rect.width / 2 - e.offsetX) / 10;
    const y =
      e.offsetY <= rect.height / 2
        ? (rect.height / 2 - e.offsetY) / 10
        : (rect.height / 2 - e.offsetY) / 10;
    ```

  - css ์ฒ๋ฆฌ ํด์ฃผ๊ธฐ

    ```js
    card.style.transform = `perspective(1000px) rotateX(${y}deg) rotateY(${-x}deg) `;
    ``;
    ```

    - ์ฃผ์ ํ ์ 
      ![์ขํ ์์](https://user-images.githubusercontent.com/44540726/132213812-f0a7e243-4150-42ca-b6bb-73527fb7f9fc.png)
      - perspective๋ฅผ ํ ๊ฒฝ์ฐ, x๋ ํ๋ฉด ์์ชฝ์ผ๋ก ๋์ค๋ ๋ฐฉํฅ์ด๋ค.
      - y๋ ์์ผ๋ก ๋๋ ๋ฐฉํฅ์ด๋ค.
      - ๋ฐ๋ผ์ rotateX()์ y๋ฅผ ๋ฃ์ด์ฃผ๊ณ  rotateY์ x๋ฅผ ๋ฃ์ด์ค๋ค.

---

### ๋ฆฌ๋ทฐ

- ์ ์ ํ ๊ฐ๋๊ฐ์ ๋์ค๊ฒ ํ๋ ๋ก์ง์ ์๊ฐํ๋๋ฐ ์๊ฐ์ด ๋ง์ด ๊ฑธ๋ ธ๋ค. ๋๋ต -20deg ~ 20deg๋ง ์๋ค๊ฐ๋ค ํ๊ณ ์ถ์๊ธฐ ๋๋ฌธ์...
- ํ์ฌ ๋ง์ฐ์ค ์์น๊ฐ ์์์ ํฌ๊ธฐ์ ๋ฐ๋ณด๋ค ์์ ๊ฒฝ์ฐ์ ํฐ ๊ฒฝ์ฐ ๋๊ฐ์ง๋ฅผ ์๊ฐํด์ ๊ฐ๋๋ฅผ ๊ณ์ฐํ๋ค.
- z์ขํ๊ฐ ๋ด ๋ฐฉํฅ์ผ๋ก ๋์ค๋ ์ค ์์๋๋ฐ, x์ขํ๊ฐ ๋ด ๋ฐฉํฅ์ผ๋ก ๋์ค๋ ๊ฒ์ด์๋ค.
