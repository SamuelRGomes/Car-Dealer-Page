<template>
  <div class="overlay">
    <h1 class="brand">Avonale</h1>
    <h1 class="title">Seguro Auto</h1>
    <p>
      Encontre as melhores ofertas de seguro de carro por um preço <br />
      justo. Faça uma cotação de seguro auto gratuita e 100% online, com <br />
      resultados na sua tela.
    </p>
    <div class="button" @click="forward">
      <button class="button-17" role="button">
        <span>COTAR MEU SEGURO</span>
      </button>
    </div>
    <div class="welcomepic">
      <img class="pic" src="../assets/welcomepic.webp" alt="" />
    </div>
    <div class="backgroundpic">
      <img class="backpic" src="../assets/background.webp" alt="" />
    </div>
    <a href="tel:+7930258910">
      <div class="telefone">
        <img src="../assets/icon-phone-1.svg" alt="" />
        <span> (79) 3025 8910</span>
      </div>
    </a>
  </div>
  <GoBackButton @click="this.$router.replace('/atendente')"></GoBackButton>
  <LogoutButtonVue color="white"></LogoutButtonVue>
</template>
<script>
import LogoutButtonVue from "./LogoutButton.vue";
import GoBackButton from "./GoBackButton.vue";
import { ref } from "vue";
import { onBeforeRouteLeave, useRouter } from "vue-router";
export default {
  components: { GoBackButton, LogoutButtonVue },
  setup() {
    const router = useRouter();
    onBeforeRouteLeave((to) => {
      if (to.path == "/seguro" && !confirmRoute.value) {
        router.replace("/atendente");
      }
    });
    let confirmRoute = ref(false);
    function forward() {
      confirmRoute.value = true;
      router.push("/seguro");
    }
    return {
      forward,
    };
  },
};
</script>
<style scoped>
.telefone {
  position: absolute;
  top: -8.7%;
  left: 80.1%;
}
.telefone > span {
  font-family: Open Sans, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI,
    Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji,
    Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
  color: rgb(112 112 112);
  font-size: 14.2px;
  margin-left: 38px;
  margin-top: -26.3px;
  display: block;
  font-weight: 500;
}
.telefone > img {
  width: 22px;
}
.brand {
  position: absolute;
  font-family: "Product Sans";
  color: rgb(40 57 204);
  top: -15.5%;
  left: 9%;
  cursor: pointer;
  font-size: 2.1rem;
  letter-spacing: 1.5px;
}

.pic {
  width: 46.451%;
  z-index: 100;
}
.welcomepic {
  bottom: 0;
  right: 0;
  width: 36%;
  position: absolute;
}
.backpic {
  width: 1028px;
  z-index: 2;
}
.backgroundpic {
  left: 10.6%;
  bottom: 0;
  position: absolute;
  z-index: -2;
}

@font-face {
  font-family: "Product Sans";
  font-style: normal;
  font-weight: 400;
  src: local("Open Sans"), local("OpenSans"),
    url(https://fonts.gstatic.com/s/productsans/v5/HYvgU2fE2nRJvZ5JFAumwegdm0LZdjqr5-oayXSOefg.woff2)
      format("woff2");
}
p {
  font-size: 1rem;
  color: white;
  font-family: Open Sans, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI,
    Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji,
    Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
  position: absolute;
  top: 30%;
  left: 18.45%;
}
.title {
  position: absolute;
  top: 17.5%;
  left: 18.45%;
  font-family: Poppins, Open Sans, system-ui, -apple-system, BlinkMacSystemFont,
    Segoe UI, Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif,
    Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
  font-size: 1.9rem;
  font-weight: 700;
  color: white;
  line-height: 1.4;
}
.overlay {
  top: 8%;
  right: 0;
  position: absolute;
  width: 100%;
  height: 65%;
  z-index: -100;
  background: rgb(40 57 204);
}
.button {
  position: absolute;
  left: 18.3%;
  top: 55.55%;
}
.button-17 {
  align-items: center;
  appearance: none;
  background-color: rgb(249 212 35);
  border-radius: 24px;
  border-style: none;
  box-shadow: rgba(0, 0, 0, 0.2) 0 3px 5px -1px,
    rgba(0, 0, 0, 0.14) 0 6px 10px 0, rgba(0, 0, 0, 0.12) 0 1px 18px 0;
  box-sizing: border-box;
  cursor: pointer;
  display: inline-flex;
  fill: currentcolor;
  font-family: "Google Sans", Roboto, Arial, sans-serif;
  font-size: 14px;
  font-weight: 500;
  justify-content: center;
  letter-spacing: 0.25px;
  line-height: normal;
  max-width: 100%;
  overflow: visible;
  padding: 2px 24px;
  position: relative;
  text-align: center;
  text-transform: none;
  transition: box-shadow 280ms cubic-bezier(0.4, 0, 0.2, 1),
    opacity 15ms linear 30ms, transform 270ms cubic-bezier(0, 0, 0.2, 1) 0ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: auto;
  will-change: transform, opacity;
  z-index: 0;
  width: 290px;
  color: rgb(51 51 51 / var);
  font-family: Open Sans, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI,
    Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji,
    Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
  font-weight: 500;
  font-size: 0.84rem;
  letter-spacing: 0.06em;
  word-spacing: -1px;
  height: 2.8rem;
}

.button-17:hover {
  background-color: #ffb347;
}

.button-17:active {
  box-shadow: 0 4px 4px 0 rgb(60 64 67 / 30%),
    0 8px 12px 6px rgb(60 64 67 / 15%);
  outline: none;
}

.button-17:focus {
  outline: none;
  border: 2px solid #4285f4;
}

.button-17:not(:disabled) {
  box-shadow: rgba(60, 64, 67, 0.3) 0 1px 3px 0,
    rgba(60, 64, 67, 0.15) 0 4px 8px 3px;
}

.button-17:not(:disabled):hover {
  box-shadow: rgba(60, 64, 67, 0.3) 0 2px 3px 0,
    rgba(60, 64, 67, 0.15) 0 6px 10px 4px;
}

.button-17:not(:disabled):focus {
  box-shadow: rgba(60, 64, 67, 0.3) 0 1px 3px 0,
    rgba(60, 64, 67, 0.15) 0 4px 8px 3px;
}

.button-17:not(:disabled):active {
  box-shadow: rgba(60, 64, 67, 0.3) 0 4px 4px 0,
    rgba(60, 64, 67, 0.15) 0 8px 12px 6px;
}

.button-17:disabled {
  box-shadow: rgba(60, 64, 67, 0.3) 0 1px 3px 0,
    rgba(60, 64, 67, 0.15) 0 4px 8px 3px;
}
@media screen and (max-width: 1300px) {
  .backpic {
    width: 1015px;
    z-index: 2;
  }
  .welcomepic {
    bottom: 0;
    right: -120px;
    width: 39%;
    position: absolute;
  }
}
@media screen and (max-width: 1168.73px) {
  .welcomepic {
    bottom: 0;
    right: -120px;
    width: 42%;
    position: absolute;
  }
  .brand {
    left: 11%;
  }
  .telefone {
    left: 78%;
  }
}
@media screen and (max-width: 1115.73px) {
  .brand {
    left: 12%;
  }
  .telefone {
    left: 76%;
  }
}
@media screen and (max-width: 1075.64px) {
  .welcomepic {
    bottom: 0;
    right: -180px;
    width: 46%;
    position: absolute;
  }
  .brand {
    left: 12%;
  }
  .telefone {
    left: 76%;
  }
}
@media screen and (max-width: 1024.64px) {
  .brand {
    left: 12.2%;
  }
  .telefone {
    left: 74%;
  }
}
@media screen and (max-width: 1008.19px) {
  .welcomepic {
    bottom: 0;
    right: -200px;
    width: 49%;
    position: absolute;
  }
  .brand {
    left: 12.5%;
  }
  .telefone {
    left: 72%;
  }
}
@media screen and (max-width: 908.36px) {
  .welcomepic {
    bottom: 0;
    right: -200px;
    width: 49%;
    position: absolute;
    display: none;
  }
  .backpic {
    display: none;
  }
  .brand {
    left: 14%;
  }
  .telefone {
    left: 72%;
  }
  @media screen and (max-width: 908.36px) {
    .brand {
      left: 14.8%;
    }
    .telefone {
      left: 70%;
    }
  }
  @media screen and (max-width: 794.36px) {
    .brand {
      left: 15.8%;
    }
    .telefone {
      left: 68%;
    }
  }
  @media screen and (max-width: 794.36px) {
    .brand {
      left: 15.8%;
    }
    .telefone {
      left: 67%;
    }
  }
  @media screen and (max-width: 719.36px) {
    .brand {
      left: 17.5%;
    }
    .telefone {
      left: 65%;
    }
  }
  @media screen and (max-width: 677.36px) {
    .brand {
      left: 18.5%;
    }
    .telefone {
      left: 62%;
    }
  }
  @media screen and (max-width: 646.36px) {
    .brand {
      left: 19.5%;
    }
    .telefone {
      left: 60%;
    }
  }
  @media screen and (max-width: 598.55px) {
    .brand {
      left: 19.5%;
    }
    .telefone {
      left: 58%;
    }
  }
}
</style>
