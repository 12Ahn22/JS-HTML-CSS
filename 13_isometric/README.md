## ๐13_isometric

- BEM ๋ฐฉ๋ฒ๋ก  ์ฌ์ฉ

**CSS๋ก Isometric ํจ๊ณผ์ฃผ๊ธฐ**

---

[์ ํ๋ธ๋งํฌ](https://www.youtube.com/watch?v=C8wSNZqktOM)

![13๋ ์ด์ดํจ๊ณผ20210907_192750](https://user-images.githubusercontent.com/44540726/132329914-db2c425a-6aa2-42b9-be1d-5b7266c69c9d.gif)

## ๊ณต๋ถ

### `transform-style: preserve-3d;`

ํด๋น ์์ฑ์ ๊ฐ์ง ์์๋ฅผ ๋ถ๋ชจ ์์๋ฅผ ๊ธฐ์ค์ผ๋ก 3์ฐจ์์ผ๋ก ์ค์ ํ๋ค.

- ์์๋์ง์๋๋ค.

### ์์ฒด๊ฐ ์ฃผ๊ธฐ

ํด๋น ์์์ ๋๊ป๋ฅผ ํ์ํ๊ธฐ ์ํด์ `::before`์ `::after` ๊ฐ์ ์์๋ฅผ ์ฌ์ฉํ๋ค.

- ๊ฐ์ ์์ ::์ ๊ฐ์ ํด๋์ค :๋ ๋ค๋ฅด๋ค.
  - ๊ฐ์ ์์์ธ `::before`
    - ์ ํํ ์์์ `ํน์  ๋ถ๋ถ`์ ์คํ์ผ์ ์ ์ฉํ๊ณ  ์ถ์ ๊ฒฝ์ฐ ์ฌ์ฉํ๋ค.
  - ๊ฐ์ ํด๋์ค์ธ `:hover`
    - ์ ํํ ์์๊ฐ `ํน์ ํ ์ํ`์ผ ๋, ์คํ์ผ์ ์ ์ฉํ๊ณ  ์ถ์ ๊ฒฝ์ฐ ์ฌ์ฉํ๋ค.

layer_box\_\_item์ ๋๊ป๋ฅผ ํํํ๋ ๊ฐ์ ์์ ์ฝ๋

```css
.layer_box .layer_box__item::before {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 100%;
  height: 10px;
  background: #2a2a2a;
  transform-origin: top;
  transform: skewX(-45deg);
}
.layer_box .layer_box__item::after {
  content: '';
  position: absolute;
  top: 0;
  left: -10px;
  width: 10px;
  height: 100%;
  background: #2a2a2a;
  transform-origin: right;
  transform: skewY(-45deg);
}
```

### ๋ ์ด์ด ํํํ๊ธฐ

`span` ํ๊ทธ๋ฅผ ์ฌ์ฉํด ๋ง์ฐ์ค hover์, ๊ฐ๊ฐ span๋ค์ด ์์น๋ฅผ ๋ณ๊ฒฝํด ์ธต์ด ์์ธ ํจ๊ณผ๋ฅผ ํํํ๋ค.

- `transform: translate(30px, -30px);`
  - transform์ ์ฌ์ฉํด ์์น๋ฅผ ๋ณ๊ฒฝํ  ๋, ๋ณ๊ฒฝ ๊ธฐ์ค์ ํ์ฌ ์์์ ์์น๋ฅผ ๊ธฐ์ค์ผ๋ก ํ๋ค.
  - ๋ฐ๋ผ์, 30px, -30px์ ํ์ฌ ์์น์์ 30px์ ์ด๋ํ๋ค.
