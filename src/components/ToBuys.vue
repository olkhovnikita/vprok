<template>
  <div class="container">
    <div class="blocks">
      <div class="block">
        <div class="img-wrap">
          <img class="img" src="/img/toBuys/discount.png" alt="pic" />
        </div>
        <div class="text-wrap">
          <div class="title">
            Скидка <br />
            <span>1500 ₽</span>
          </div>
          <div class="desc">–500 ₽ на первые три заказа по промокоду NEW</div>
        </div>
      </div>
      <p>+</p>
      <div class="block">
        <div class="img-wrap">
          <img class="img" src="/img/toBuys/delivery.png" alt="pic" />
        </div>
        <div class="text-wrap">
          <div class="title">
            Бесплатная <br />
            <span>доставка</span>
          </div>
          <div class="desc">первого заказа</div>
        </div>
      </div>
    </div>
    <button class="to_buys_btn" type="button" @click="onChangeModal">
      К покупкам
    </button>
    <div class="modal" v-if="showModal">
      <div class="modal-content">
        <form id="app" @submit="checkForm">
          <p>
            {{ errors }}
          </p>
          <p>
            <label for="email">email</label>
            <input id="email" v-model="email" type="email" name="email" />
          </p>
          <p>
            <button type="submit" class="send_btn">Отправить</button>
          </p>
          <p v-if="message != ''">{{ message }}</p>
        </form>
        <button class="close_btn" type="button" @click="onChangeModal">
          Закрыть
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToBuys",
  data() {
    return {
      loading: false,
      message: "",
      errors: "",
      showModal: false,
      email: "",
    };
  },
  methods: {
    onChangeModal: function () {
      if (!this.showModal) {
        this.showModal = true;
      } else {
        this.message = "";
        this.showModal = false;
      }
    },

    checkForm: function (e) {
      e.preventDefault();
      this.errors = "";
      if (!this.email) {
        this.errors = "Требуется указать email.";
        return;
      }
      var re = /\S+@\S+\.\S+/;
      if (!re.test(this.email)) {
        this.errors = "Неправильный email";
        return;
      }
      e.target.reset();
      this.loading = true;

      setTimeout(() => {
        console.log(this.email);
        this.message = "Спасибо";
        this.errors = "";
        this.email = "";
      }, 1000);

      this.loading = false;
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #fff;
  padding: 60px 60px 100px;
  border: 2px solid yellow;
}
.blocks {
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: space-between;
  flex-wrap: wrap;
}

.block {
  border: 1px solid #d0d4cd;
  margin: 0 20px;
  width: 390px;
  height: 220px;
  padding: 24px;
  display: flex;
  flex-direction: row;
}
.img-wrap {
  height: 70px;
  width: 70px;
  background-color: #7db945;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  flex-shrink: 0;
}
.img {
  object-fit: cover;
  align-self: center;
}

.text-wrap {
  text-align: left;
  margin: 11px 30px;
}

p {
  font-size: 20px;
  font-family: RotondaC;
}

.title {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  color: #26303b;
}

span {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  color: #7db945;
}

.desc {
  padding-top: 15px;
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 16px;
  font-weight: 300;
}

.modal {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
  bottom: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: wheat;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  overflow-y: auto;
  width: 50vw;
  height: 50vh;
  max-width: 600px;
  max-height: 400px;
}

#email {
  padding: 5px 10px;
  margin: 0 5px;
}

.to_buys_btn {
  background: linear-gradient(0deg, #7db945, #7db945), #7db945;
  border-radius: 10px;
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 22px;
  text-align: center;
  color: #ffffff;
  padding: 17px 110px;
  margin: 50px 100px;
}

.close_btn {
  position: absolute;
  top: 5px;
  right: 5px;
  background-color: red;
  color: white;
  padding: 10px;
}

@media (max-width: 1024px) {
  .modal-content {
    width: 70vw;
  }
  .blocks {
    flex-direction: column;
    width: 100%;
  }
  .block {
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 90vw;
    max-width: 350px;
  }

  .text-wrap {
    margin: 0;
    text-align: center;
  }

  .to_buys_btn {
    padding: 17px 80px;
  }

  .container {
    padding: 0;
  }
}
</style>