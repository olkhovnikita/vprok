<template>
  <div class="border">
    <p class="adv_text">Преимущества даркстора</p>
    <div class="container">
      <div class="advantages" v-for="adv in advantage" :key="adv">
        <div class="adv-img-wrap">
          <img :src="`${adv.img}`" class="adv-img" />
        </div>
        <div class="title">{{ adv.title }}</div>
        <div class="desc">{{ adv.desc }}</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Advantages",
  data() {
    return {
      advantage: [
        {
          id: 0,
          img: "/img/advantage/apple.png",
          title: "Нет контакта с посторонними людьми",
          desc: "Заказ формируется из товаров, до которых никто не дотрагивался, как это возможно на полках обычного магазина. Фрукты и овощи отбираются сборщиком вручную.",
        },
        {
          id: 1,
          img: "/img/advantage/freeze.png",
          title: "Заморозка 1 раз",
          desc: "Продукты замораживаются однократно и поддерживаются в этом состоянии, пока не будут доставлены к вам. ",
        },
        {
          id: 2,
          img: "/img/advantage/cameras.png",
          title: "Профессиональные морозильные камеры",
          desc: "Товар хранится в промышленных холодильных и морозильных зонах с оптимальными температурными режимами для разных товаров: овощей, фруктов, масла и т. д.",
        },
        {
          id: 3,
          img: "/img/advantage/meat.png",
          title: "Разделка мяса и рыбы под заказ",
          desc: "Мясо и рыба разделываются непосредственно для вас, а при транспортировке хранятся в специальных боксах с низкой температурой.",
        },
        {
          id: 4,
          img: "/img/advantage/bag.png",
          title: "Своя пекарня",
          desc: "Знак «Печём сами» на карточках товаров означает, что мы привезём вам свежеиспечённый тёплый хлеб.",
        },
        {
          id: 5,
          img: "/img/advantage/man.png",
          title: "Работаем с 1995 года",
          desc: "Мы занимаемся продуктами с 1995 года — все процессы хранения и доставки отточены до мелочей.",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
.border {
  border: 2px solid green;
}
.adv-img-wrap {
  height: 100px;
  display: flex;
}
.adv-img {
  object-fit: cover;
  align-self: center;
}

.advantages {
  width: 285px;
  max-height: 100%;
  max-width: 100%;
  background-color: #fff;
  margin: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 29px 17px;
  text-align: center;
  border-radius: 10px;
}

.container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  align-items: flex-start;
  margin: 42px 0;
}

.title {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 16px;
  padding: 30px;
}

.desc {
  font-family: RotondaC;
  font-style: normal;
  font-size: 16px;
}
.adv_text {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  text-align: center;
  color: #26303b;
}

@media (max-width: 1024px) {
  .title,
  .desc {
    font-size: 16px;
  }

  .adv-img-wrap {
    height: 50px;
  }
}
</style>