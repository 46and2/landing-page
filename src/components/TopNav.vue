<template>
  <header>
    <div id="container">
      <button class="toggle-button" @click="toggleMenu">
      <span class="toggle-bar"></span>
      <span class="toggle-bar"></span>
      <span class="toggle-bar"></span>
      </button>
      <div id="logo-wrapper">
        <img src="../assets/logo.svg" alt="Logo">
      </div>
      <div id="top-menu">
        <div id="top-info">
          <a href="tel:89625206378">
          <img src="@/assets/phone.png" alt="call">
          8 (962) 520-63-78
          </a>
          <a href="#">
          <img src="@/assets/location.png" alt="location">
          Уфа, Пушкина, д. 114/2
          </a>
          <a class="calc" href="#">
          <img src="@/assets/calc.png" alt="calculate">
          Расчет стоимости дома
          </a>
          <a class="mortgage" href="#">
          <img src="@/assets/mortgage.png" alt="call">
          Trade-In и Ипотека
          </a>
        </div>
        <nav>
          <ul>
            <li><a href="#" class="menu-item">Строительство</a></li>
            <li><a href="#" class="menu-item">Проекты</a></li>
            <li><a href="#" class="menu-item">Наши работы</a></li>
            <li><a href="#" class="menu-item">Земельные участки</a></li>
            <li><a href="#" class="menu-item">Услуги&#8964;</a></li>
            <li><a href="#" class="menu-item">О компании</a></li>
            <li><a href="#" class="menu-item">Контакты</a></li>
          </ul>
        </nav>
      </div>
      <a href="tel:89625206378" class="call-button">
      <img src="@/assets/call.png" alt="call">
      </a>
    </div>
    <nav class="hidden" :class="{responsive:showMenu}">
      <ul>
        <li><a href="#" class="menu-item">Строительство</a></li>
        <li><a href="#" class="menu-item">Проекты</a></li>
        <li><a href="#" class="menu-item">Наши работы</a></li>
        <li><a href="#" class="menu-item">Земельные участки</a></li>
        <li><a href="#" class="menu-item">Услуги&#8964;</a></li>
        <li><a href="#" class="menu-item">О компании</a></li>
        <li><a href="#" class="menu-item">Контакты</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'TopNav',
  data() {
    return {
      showMenu: false,
    };
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    },
  },
};
</script>

<style>
header {
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.18);
}

#container {
  display: flex;
  align-items: center;
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  max-width: 1150px;
}

nav {
  width: 100%;
  display: flex;
}

#top-menu {
  padding: 15px 0 0 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: calc(100% - 214px);
}

nav ul,
#top-info {
  display: flex;
  justify-content: space-between;
  width: 100%;
  padding: 0;
}

#top-info a {
  text-decoration: none;
  color: #000;
  display: flex;
  align-items: center;
  font-size: 16px;
  font-weight: 600;
}

#top-info a img {
  padding-right: 10px;
}

.calc,
.mortgage {
  border-bottom: 1px dashed;
}

.calc:hover,
.mortgage:hover {
  border-bottom: 1px dashed #ffffff;
}

#top-info a.calc {
  color: #b79b6c;
}

nav ul li {
  list-style: none;
}

.menu-item {
  text-decoration: none;
  color: #000;
  cursor: pointer;
}

.menu-item:hover {
  text-shadow: 0 0 .65px #333, 0 0 .65px #333;
}

#logo-wrapper {
  width: 214px;
}

.toggle-button,
.call-button {
  width: 53px;
  height: 40px;
  padding: 10px 10px;
  background-color: transparent;
  border: 1px solid #b79b6c;
  display: none;
  align-items: flex-start;
  flex-direction: column;
  justify-content: space-between;
  outline: none;
  cursor: pointer;
}

.toggle-button {
  border-radius: 0 5px 5px 0;
  border-left: none;
}

.call-button {
  border-radius: 5px 0 0 5px;
  border-right: none;
  align-items: center;
}

.toggle-button .toggle-bar {
  display: block;
  width: 28px;
  height: 4px;
  background-color: #b79b6c;
  border-radius: 4px;
  position: static;
}

.toggle-button .toggle-bar:first-child {
  top: calc(50% - 2px) !important;
  left: calc(50% - 13px) !important;
}

.toggle-button .toggle-bar:nth-child(2) {
  width: 23px;
}

.toggle-button .toggle-bar:last-child {
  top: calc(50% - 2px) !important;
  left: calc(50% - 13px) !important;
}

.hidden {
  display: none;
}

.responsive {
  display: inline;
}

.responsive ul {
  margin-top: 0;
  padding-left: 10px;
}

.responsive ul li {
  line-height: 2;
}

@media (max-width: 992px) {
  ul {
    flex-direction: column;
  }
  .toggle-button,
  .call-button {
    display: flex;
  }
  .call-button {
    padding: 0;
    display: flex;
    justify-content: space-around;
  }
  #container {
    height: 79px;
  }
  #top-menu {
    display: none;
  }
  #logo-wrapper {
    width: 157px;
  }
}
</style>
