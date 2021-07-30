<template>
  <div class="container">
    <div class="logo">
      <img src="/img/header/logo.png" alt="vprok" />
    </div>
    <div class="contacts_wrap">
      <div class="contacts">
        <p class="city">Москва</p>
        <a class="tel" href="tel:+7 495 797-57-77">+7 495 797-57-77</a>
      </div>
      <div class="contacts">
        <p class="city">Санкт-Петербург</p>
        <a class="tel" href="tel:+7 812 385-99-55">+7 812 385-99-55</a>
      </div>
    </div>
    <div class="social">
      <a href="#" class="link" target="_blank"
        ><img src="/img/footer/fb.png" alt="fb" />
      </a>
      <a href="#" class="link" target="_blank"
        ><img src="/img/footer/vk.png" alt="vk" />
      </a>
      <a href="#" class="link" target="_blank"
        ><img src="/img/footer/in.png" alt="in" />
      </a>
      <a href="#" class="link" target="_blank"
        ><img src="/img/footer/ok.png" alt="ok" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.container {
  background: url(/img/footer/footer_img.png);
  padding: 47px 262px 111px;
    border: 2px solid red;
}
.city {
  font-family: RotondaC;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  color: #ffffff;
  padding: 10px 0;
}
.contacts_wrap {
  display: flex;
  justify-content: flex-start;
  flex-direction: row;
}

.contacts {
  padding: 20px 40px 0 0;
}
.tel {
  font-family: RotondaC;
  font-style: normal;
  font-weight: bold;
  font-size: 22px;
  color: #ffffff;
}

.social {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  margin-top: -35px;
  align-items: center;
}

.link {
  margin: 0 40px;
}

@media (max-width: 1024px) {
  .container {
    padding: 50px 70px;
    flex-direction: column;
  }

  .contacts_wrap {
    padding-top: 10px;
    flex-direction: column;
  }

  .contacts {
    padding: 0;
  }
  .social {
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
    margin: 0;
  }

  .link {
    margin: 20px 0;
  }
}
</style>