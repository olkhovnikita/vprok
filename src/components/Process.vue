<template>
  <div class="wrap">
    <p class="process-text">Взгляните на процесс сборки своими глазами</p>
    <div class="process-content">
      <button
        class="left_arrow"
        type="button"
        @click="prevSlide"
        :disabled="slideId == 0"
      >
        <img src="/img/process/left-arrow.png" alt="arrow" />
      </button>
      <div class="img-wrap">
        <p class="slide-num">{{ slideId + 1 }}</p>
        <img class="img" :src="`${slides[slideId].img}`" alt="pic" />
        <p class="title">{{ slides[slideId].title }}</p>
        <p class="desc">{{ slides[slideId].desc }}</p>
      </div>
      <button
        class="right_arrow"
        type="button"
        @click="nextSlide"
        :disabled="slides.length == slideId + 1"
      >
        <img src="/img/process/right-arrow.png" alt="arrow" />
      </button>
    </div>
    <div class="bottom_btns">
      <button type="button" @click="prevSlide" :disabled="slideId == 0">
        <img src="/img/process/left-arrow.png" alt="arrow" />
      </button>
      <button
        type="button"
        @click="nextSlide"
        :disabled="slides.length == slideId + 1"
      >
        <img src="/img/process/right-arrow.png" alt="arrow" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Process",
  data() {
    return {
      loading: false,
      slideId: 0,
      slides: [
        {
          img: "/img/process/accuracy.png",
          title: "Привезём точно по списку",
          desc: "Сборщик берëт с собой наручный терминал, на котором он видит весь список покупок для каждого заказа.",
        },
        {
          img: "/img/process/fast.png",
          title: "Собираем быстро и эффективно",
          desc: "Для улучшения эргономики пространства товары размещены от тяжëлых к лëгким, находящимся уже в конечной зоне упаковки.",
        },
        {
          img: "/img/process/fresh.png",
          title: "За свежесть и качество отвечаем",
          desc: "Выделены специальные зоны, в том числе холодная и морозильная",
        },
        {
          img: "/img/process/shampoo.png",
          title: "Шампунь не положат рядом с рыбой",
          desc: "Собираем и упаковываем ваш заказ с заботой: соблюдаем принципы товарного соседства и учитываем вес товара.",
        },
        {
          img: "/img/process/eggs.png",
          title: "Довезëм в сохранности даже яйца",
          desc: "Бережно транспортируем контейнеры, фиксируя их стяжными ремнями. Системы охлаждения поддерживают температурный режим.",
        },
      ],
    };
  },
  methods: {
    nextSlide: function () {
      if (this.slides.length == this.slideId + 1) {
        return;
      } else {
        this.slideId++;
      }
    },
    prevSlide: function () {
      if (this.slides.length != 0) {
        this.slideId--;
      }
    },
  },
};
</script>

<style scoped>
.bottom_btns {
  display: none;
}
.wrap {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: center;
  max-width: 690px;
  margin: 129px auto 80px;
  border: 2px solid blue;
}
.process-text {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  text-align: center;
  margin-bottom: 30px;
}

.process-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 20px;
}

.img {
  max-width: 560px;
}
.img-wrap {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;
  flex-direction: column;
  padding: 40px 25px;
  position: relative;
}

.slide-num {
  position: absolute;
  top: 30px;
  left: 15px;
  background-color: #fff;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  color: #7db945;
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  width: 50px;
  background-color: transparent;
  margin: 0 15px;
}

.title {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 16px;
  text-align: center;
  color: #26303b;
  padding: 20px 0 15px;
}

.desc {
  font-family: RotondaC;
  font-size: 16px;
  font-weight: 300;
  text-align: center;
  color: #26303b;
  max-width: 500px;
}

@media (max-width: 1024px) {
  .left_arrow,
  .right_arrow {
    display: none;
  }

  .img-wrap {
    width: 90vw;
  }

  .img {
    width: 100%;
  }
  .bottom_btns {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 50px 0;
  }
  .process-text {
    font-size: 26px;
  }
}
</style>