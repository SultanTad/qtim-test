<template>
  <header class="header">
    <NuxtLink to="/">
      <img class="header__logo" src="../assets/images/Qtim.png" alt="" />
    </NuxtLink>
    <nav class="nav">
      <ul class="menu__list">
        <li class="menu__item">
          <NuxtLink to="/">Works</NuxtLink>
        </li>
        <li class="menu__item">
          <NuxtLink to="/">About</NuxtLink>
        </li>
      </ul>
      <div class="nav__inner">
        <img
          class="menu__item-img"
          src="../assets/images/unitedkingdom.png"
          alt=""
        />
        <button class="menu__item-btn">Let’s work</button>
      </div>
    </nav>
  </header>
</template>

<style>
.header {
  padding: 35px 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header a {
  font-family: "TTCommons-Regular";
  font-size: 20px;
  color: rgb(16, 16, 16);
}

.nav {
    display: flex;
    align-items: center;
}

.nav__inner {
    display: flex;
    align-items: center;
    gap: 0 16px;
}

.nav__inner img {
    border-radius: 100%;
    border: 2px solid rgba(0, 0, 0, 0.1);
    padding: 14px;
}

.nav__inner button {
    color: #fff;
    font-size: 20px;
    background: #000;
    padding: 16px 32px;
    border-radius: 999px;
    border: none
}

.menu__list {
  display: flex;
  align-items: center;
  gap: 0 50px;
  margin-right: 85px;
}
</style>
