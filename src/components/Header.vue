<template>
  <header class="header">
    <div class="header__logo">
      <img class="header__logo-img" />
      <p class="header__logo-title">Logo</p>
    </div>
    <input id="nav-toggle" class="header__toggle" type="checkbox">
    <label class="header__btn" for='nav-toggle'>
        <span></span>
    </label>

    <nav class="header__nav">
      <a class="header__link">Link 1</a>
      <a class="header__link">Link 1</a>
      <a class="header__link">Link 1</a>
      <a class="header__link">Link 1</a>
      <a class="header__link">Link 1</a>
      <a class="header__link">Link 1</a>
    </nav>
  </header>
</template>

<style scoped>
.header {
  max-width: 360px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  margin: 0 auto;
  padding: 0 20px;
  background: #ffffff;
  flex-wrap: wrap;
  position: relative;
}
.header__logo {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.header__logo-img {
  width: 25px;
  height: 25px;
  background: #c4c4c4;
}
.header__logo-title {
  margin-left: 10px;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 11px;
  line-height: 13px;
}
.header__toggle{
    opacity: 0;
}
.header__btn{
  display: flex; 
  align-items: center;  
  width: 25px;
  height: 17px;
  cursor: pointer;
  z-index: 1;
}
.header__btn > span,
.header__btn > span::before,
.header__btn > span::after {
  display: block;
  position: absolute;
  width: 25px;
  height: 3px;
  background-color: #C4C4C4;
}
.header__btn > span::before {
  content: '';
  top: -7px;
}
.header__btn > span::after {
  content: '';
  top: 7px;
}

.header__nav {
  display: none;
  visibility: hidden;
  max-width: 360px;
  width: calc(100% - 40px);
  position: absolute;
  top: 35px;
  right: -200%;
  flex-direction: column;
  align-items: flex-end;
  padding: 15px 20px;
  border-top: 1px solid #c4c4c4;
  background: #fff;
  object-fit: cover;
}
.header__link {
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 25px;
  line-height: 29px;
  margin-bottom: 25px;
  cursor: pointer;
}
.header__link:hover{
    opacity: .6;
}
.header__link:last-child {
  margin-bottom: 0;
}
.header__toggle:checked ~ .header__btn > span {
  transform: rotate(45deg);
}
.header__toggle:checked ~ .header__btn > span::before {
  top: 0;
  transform: rotate(0);
}
.header__toggle:checked ~ .header__btn > span::after {
  top: 0;
  transform: rotate(90deg);
}
.header__toggle:checked ~ .header__nav{
    display: flex;
  visibility: visible;
  left: 0;
}
.header__btn > span,
.header__btn > span::before,
.header__btn > span::after {
  transition-duration: .25s;
}
.header__nav {
  transition-duration: 1s;
}

</style>