<template>
  <div class="footer">
    <div class="footer__container">
      <div class="footer__container__wrapper">
        <div class="footer__container__wrapper__top">
          <div class="footer__container__wrapper__top__title">Get In Touch</div>
          <div class="footer__container__wrapper__top__body">
            I’m currently open to new opportunities, inbox is always open! Find
            me everywhere ahmadraihan015@gmail.com
          </div>
          <div class="footer__container__wrapper__top__icon">
            <a
              target="_blank"
              href="https://www.linkedin.com/in/ahmad-raihan-akhdani-202104154/"
            >
              <v-icon icon="mdi-linkedin"></v-icon>
            </a>
            <a target="_blank" href="https://github.com/ahmadraihann">
              <v-icon icon="mdi-github"></v-icon>
            </a>
            <a
              target="_blank"
              href="https://www.instagram.com/ahmad.rayhann/?hl=id"
            >
              <v-icon icon="mdi-instagram"></v-icon>
            </a>
            <a href="mailto:ahmadraihan015@gmail.com">
              <v-icon icon="mdi-email"></v-icon>
            </a>
          </div>
        </div>
        <div class="footer__container__wrapper__line">
          <div></div>
        </div>
        <div class="footer__container__wrapper__bottom">
          <div>&copy; 2023 Ahmad Raihan Akhdani All Rights Reserved</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "@/public/scss/abstracts/global" as *;
.footer {
  background: #d6d9dd;
  &__container {
    max-width: $max-width;
    margin: 0 auto;
    padding: 20px 100px 20px 100px;
    &__wrapper {
      background-image: url("/images/footer-pattern.svg");
      background-position: center center;
      background-repeat: no-repeat;
      text-align: center;
      width: 100%;
      &__top {
        padding: 120px 0 100px 0;
        &__title {
          font-family: "Raleway";
          font-style: normal;
          font-weight: 700;
          font-size: 72px;
          line-height: 85px;
          text-align: center;
          letter-spacing: 0.015em;
          text-transform: capitalize;
          color: #2d2d2d;
          margin-bottom: 30px;
        }
        &__body {
          font-family: "Lato";
          font-style: normal;
          font-weight: 400;
          font-size: 18px;
          line-height: 130%;
          text-align: center;
          letter-spacing: 0.01em;
          color: #929292;
          max-width: 574px;
          margin: 0 auto 30px auto;
        }
        &__icon {
          display: flex;
          gap: 20px;
          width: 100%;
          justify-content: center;
          a {
            text-decoration: none;
            color: #2d2d2d;
            i {
              cursor: pointer;
              &:hover,
              &:active {
                color: #e63946;
              }
            }
          }
        }
      }
      &__line {
        margin: 0 -100px 0 -100px;
        padding: 0 20px;
        div {
          border: 1px solid #848484;
        }
      }
      &__bottom {
        font-family: "Lato";
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 17px;
        color: #929292;
        padding: 50px 0 30px 0;
        text-align: center;
      }
    }
  }
}

@media (max-width: $max-width-tablet) {
  .footer {
    &__container {
      &__wrapper {
        &__top {
          padding: 90px 0 70px 0;
          &__title {
            font-size: 62px;
            line-height: 75px;
            margin-bottom: 20px;
          }
          &__body {
            font-size: 16px;
            margin: 0 auto 20px auto;
          }
        }
        &__bottom {
          padding: 40px 0 20px 0;
        }
      }
    }
  }
}

@media (max-width: $max-width-mobile) {
  .footer {
    &__container {
      padding: 20px;
      &__wrapper {
        &__top {
          padding: 50px 0 40px 0;
          &__title {
            font-size: 42px;
            line-height: 55px;
            margin-bottom: 10px;
          }
          &__body {
            font-size: 14px;
            margin: 0 auto 10px auto;
          }
        }
        &__line {
          margin: 0;
          padding: 0;
        }
        &__bottom {
          padding: 30px 0 10px 0;
        }
      }
    }
  }
}
</style>
