<template>
  <div class="header">
    <img src="/img/header/logo.png" alt="vprok" class="logo" />
    <h1 class="header-h1">Что такое Даркстор?</h1>
    <p class="desc">
      Это магазин-склад без покупателей. <br />
      Именно здесь, а не в розничном магазине собирают ваши заказы.
    </p>
    <button type="button" class="scroll" @click="scroll">
      <img src="/img/header/scroll-img.png" alt="scroll" class="scroll-img" />
      <p class="scroll-text">Свайп вниз</p>
    </button>
  </div>
</template>

<script>
export default {
  name: "Header",
  methods: {
    scroll: function () {
      let element = document.querySelector(".process");
      console.log(element);
      const y = element.getBoundingClientRect().top + window.scrollY;
      window.scroll({
        top: y,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
.header {
  background: url(/img//header/fon.png);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 100% 100%;
  padding: 65px 262px 40px;
  color: white;
  display: flex;
  flex-direction: column;
  margin-bottom: 100px;
  border: 2px solid red;
}

.header-h1 {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 54px;
  text-transform: uppercase;
  margin-top: 124px;
}

.desc {
  font-family: RotondaC;
  font-style: normal;
  font-weight: normal;
  font-size: 26px;
  max-width: 586px;
}

.logo {
  width: 150px;
  max-width: 100%;
}

.scroll {
  display: flex;
  flex-direction: row;
  align-self: center;
  align-items: center;
  justify-content: center;
  margin-top: 35px;
  background-color: transparent;
  color: #fff;
}

.scroll-img {
  width: 45px;
  max-width: 100%;
}

.scroll-text {
  padding-left: 10px;
  font-family: RotondaC;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
}

@media (max-width: 1024px) {
  .header {
    padding: 70px;
    text-align: center;
    justify-content: center;
    align-items: center;
    background-position: 60% 100%;
  }

  .header-h1 {
    font-size: 28px;
    margin-top: 70px;
  }

  .desc {
    font-size: 16px;
  }
  .scroll {
    display: none;
  }
}
</style>