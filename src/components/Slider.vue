<template>
  <div class="slider-wrapper">
    <div class="back">
      <a href="#">&lt;-- Вернуться к списку проектов</a>
    </div>
    <h1 class="slider-title">{{ title }}</h1>
    <div class="slider">
      <button class="previous" @click="getPrevious">
      <img src="@/assets/prev.png" alt="previous">
      </button>
      <img :src="require(`../assets/${images[currentIndex]}`)" class="slider-image" alt="house">
      <button class="next" @click="getNext">
      <img src="@/assets/next.png" alt="next">
      </button>
    </div>
    <div class="additional-info">
      <ul>
        <li>
          <h2>158 м<sup>2</sup></h2>
          <p>общая площадь</p>
        </li>
        <li class="delimeter"></li>
        <li>
          <h2>2</h2>
          <p>этажа</p>
        </li>
        <li class="delimeter"></li>
        <li>
          <h2>3</h2>
          <p>комнаты</p>
        </li>
        <li class="delimeter"></li>
        <li>
          <h2>1</h2>
          <p>терраса</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Slider',
  props: {
    title: String,
  },
  data() {
    return {
      images: ['house.jpg', 'house2.jpg', 'house3.jpg', 'house4.jpg'],
      currentIndex: 0,
    };
  },
  methods: {
    getPrevious() {
      this.currentIndex = (this.currentIndex - 1) % this.images.length;
    },
    getNext() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
  },
};
</script>

<style>
.slider-wrapper {
  max-width: 1150px;
  margin: 0 auto;
}

.back {
  padding-top: 40px;
}

.back a {
  font-size: 14px;
  color: #000;
}

.back a:hover {
  text-decoration: none;
}

.slider {
  display: flex;
  justify-content: center;
  align-items: center;
}

.slider-title {
  font-size: 36px;
  line-height: 1.15;
}

.slider .slider-image {
  width: 1032px;
  overflow: hidden;
  margin: 0 15px;
}

.slider button {
  background-color: #ffffff;
  border: 1px solid #b79b6c;
  height: 45px;
  width: 45px;
  outline: none;
}

.slider button:hover {
  background-color: #b79b6c;
  cursor: pointer;
}

.additional-info {
  max-width: 1032px;
  margin: 0 auto;
}

.additional-info ul {
  padding: 0 3px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  list-style: none;
}

.additional-info ul li h2 {
  color: #b79b6c;
  font-size: 48px;
  font-weight: 400;
  margin: 0;
}

.additional-info .delimeter {
  content: ' ';
  background-color: #f1f1f1;
  margin: auto 0;
  height: 75px;
  width: 2px;
}

sup {
  vertical-align: top;
  position: relative;
  top: -0.5em;
}

@media (max-width: 992px) {
  .delimeter {
    display: none;
  }
  .additional-info ul {
    flex-wrap: wrap;
    flex-direction: row;
  }
  .additional-info ul li {
    position: relative;
    width: 50%;
    padding: 10px 0 10px 20px;
    border-bottom: 2px solid #f1f1f1;
    outline: none;
    box-sizing: border-box;
  }
  .additional-info ul li:nth-child(1) h2:after,
  .additional-info ul li:nth-child(5) h2:after {
    content: '';
    position: absolute;
    top: 50%;
    right: 0;
    width: 2px;
    height: 80%;
    background-color: #f1f1f1;
    transform: translateY(-50%);
  }
}
@media (max-width: 765px) {
  .slider-wrapper {
    margin: 0 15px;
  }
  .slider {
    flex-wrap: wrap;
    justify-content: space-between;
  }
  .slider-title,
  .additional-info ul li h2 {
    font-size: 24px;
  }
  .slider .slider-image {
    margin: 0;
  }
  .slider button {
    order: 1;
    margin-top: 15px;
  }
  .additional-info p {
    margin: 5px 0 0 0 ;
    font-size: 16px;
  }
}
</style>
