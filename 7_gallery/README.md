## π7_gallery

**Gridλ₯Ό μ¬μ©ν κ°€λ¬λ¦¬ λ§λ€κΈ°**

[μ νλΈλ§ν¬](https://www.youtube.com/watch?v=sHG3Sf6XN9g)

![κ°€λ¬λ¦¬](http://drive.google.com/uc?export=view&id=1zzs60sgd6-_ipQaARGzxOp_V5VWA4nUh)

## κ³΅λΆ

### Grid

**κ·Έλ¦¬λλ?**

- 2μ°¨μ(νκ³Ό μ΄)μ λ μ΄μμ μμ€νμ μ κ³΅νλ CSS κΈ°λ₯μλλ€.
  flex box λ³΄λ€ μ’ λ κ³ μ°¨μ μ μΈ λ μ΄μμμ μν΄ μκ²¨λ¬μ΅λλ€.

**grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));**

- ν΄λΉ κ·Έλ¦¬λμ μ»¬λΌμ λͺμν΄μ€λλ€.

  repeat μμ κ°μ λ°λ³΅ν΄μ μ»¬λΌμ μμ±ν©λλ€.

- `minmax(μ΅μκ°, μ΅λκ°)`

  μ»¬λΌ μμ μμκ° κ°μ§λ μ΅μκ°κ³Ό μ΅λκ°μ μ€μ ν©λλ€. μ μ½λμμ μ΅λκ°μΌλ‘ 1frμ μ£Όλ μ΄μ λ λΆλͺ¨ μ»¨νμ΄λκ° `width:80%`λ₯Ό κ°μ§κΈ° λλ¬Έμ ν¬κΈ°κ° λ³λ λ  κ²½μ°, λ¨λ μ¬λ°±μμ΄ μ μ²΄ κ³΅κ°μ μ¬μ©νκΈ° μν΄μ μλλ€. 1frμ μ°μ§μλ κ²½μ° μ¬λ°±μ΄ λ¨κ²λ©λλ€.

- `auto-fit`κ³Ό `auto-fill`

  auto-fitκ³Ό auto-fillμ repeatλ‘ λ°λ³΅ν  νμ΄ κ°μκ° λͺνν  νμκ° μκ±°λ λͺννμ§ μμ κ²½μ° μ¬μ©

  λ΄λΆ μμκ° λΆλͺ¨ μ»¨νμ΄λμ ν¬κΈ°λ₯Ό μ΄κ³Όν  κ²½μ° μλμΌλ‘ μ€μ λ³κ²½ν©λλ€.
  auto-fitμ λ¨λ κ³΅κ°μ μΆμνκ³  auto-fillμ λ¨μ κ³΅κ°μ κ·Έλλ‘ μ μ§μν΅λλ€.

### λ«λ νκ·Έκ° μλ κ²½μ° κ°μ μμ μ¬μ©λΆκ°

`img`κ°μ΄ λ«λ νκ·Έκ° μλ κ²½μ° `before`μ `after` κ°μ κ°μ μμλ₯Ό μ¬μ©ν  μ μλ€

```css
.img-gallery img:hover {
  /* imgνκ·Έλ€μλ beforλ afterκ°μ κ°μ μμ μ¬μ© λΆκ° */
  /* transform: scale(0.8) rotate(-15deg); */
  border-radius: 20px;
  filter: grayscale(1);
}
```

### μ΄λ²€νΈ μμ

μ΄λ²€νΈ λ¦¬μ€λλ₯Ό νμ μμλ€μ μΆκ°νλ κ²μ΄ μλλΌ μμ μμμ μΆκ°νλ κ²μ λ§νλ€.

- κ° νμ ν­λͺ© νλνλμ μ΄λ²€νΈ λ¦¬μ€λλ₯Ό μ°κ²°νμ§ μκ³  μμ μμ νλμ μ΄λ²€νΈ λ¦¬μ€λλ₯Ό μ°κ²°νλ©΄ λκΈ° λλ¬Έμ λ©λͺ¨λ¦¬ μ¬μ© κ³΅κ°μ μ€μΌ μ μλ€.

μλ μ½λλ imgνκ·Έλ₯Ό ν΄λ¦­νλ©΄ μ΄λ²€νΈκ° λ°μν΄μΌνλ€.

```html
<section class="img-gallery" id="imgGallery">
  <!-- λͺ¨λ  μμμ μ΄λ²€νΈλ₯Ό κ±Έμ΄μ£Όλ κ±΄ λΆνΈ -->
  <img src="../src/img/1.jpg" alt="random" />
  <img src="../src/img/2.jpg" alt="random" />
  <img src="../src/img/3.jpg" alt="random" />
  <img src="../src/img/4.jpg" alt="random" />
  <img src="../src/img/5.jpg" alt="random" />
  <img src="../src/img/6.jpg" alt="random" />
  <img src="../src/img/7.jpg" alt="random" />
  <img src="../src/img/8.jpg" alt="random" />
</section>
```

μ΄λ²€νΈ λ¦¬μ€λλ₯Ό νμ imgνκ·Έμ λͺ¨λ μ€μ νλ κ²μ΄ μλλΌ

λΆλͺ¨μΈ `imgGallery`μ μ€μ ν ν,

- `e.target`μ `nodeName`μΌλ‘ μ΄λ²€νΈκ° μΌμ΄λ  μμλ₯Ό κ²°μ νλ€

```js
const openFullImg = (e) => {
  if (e.target.nodeName !== 'IMG') return;
  fullImgBox.classList.add('active');
  // μ΄λ²€νΈκ° μ λ¬ν κ°μ²΄
  console.log(e.target);
  // μ΄λ²€νΈ νΈλ€λ¬λ₯Ό νΈμΆνλ κ°μ²΄
  console.log(e.currentTarget);
  fullImg.src = e.target.src;
};

// μ΄λ²€νΈ μ²λ¦¬
imgGallery.addEventListener('click', openFullImg);
```

- `e.target`

  μ΄λ²€νΈκ° μ λ¬ν κ°μ²΄ = ν΄λ¦­ λ img νκ·Έ

- `e.currentTarget`

  μ΄λ²€νΈ νΈλ€λ¬λ₯Ό νΈμΆν κ°μ²΄ = imgGallery
