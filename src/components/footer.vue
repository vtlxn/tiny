<template>
  <footer class="footer">
    <div class="container">
      <div class="row flex-column">
        <div class="footer__top">
          <div class="title">
            Keep in touch with us
          </div>
          <div class="description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus
            tristique bibendum. Donec rutrum sed sem quis venenatis.
          </div>
          <form class="email-field">
            <input id="mail" type="email" placeholder="Enter your email to update" class="text-field">
            <button class="button" disabled>SUBMIT</button>
          </form>

        </div>
        <div class="footer__social">
          <a href="#"><img src="../assets/fb.png" class="social-icon" alt="fb"></a>
          <a href="#"><img src="../assets/tw.png" class="social-icon" alt="tw"></a>
          <a href="#"><img src="../assets/gp.png" class="social-icon" alt="gp"></a>
          <a href="#"><img src="../assets/pt.png" class="social-icon" alt="pt"></a>
        </div>
        <div class="footer-bottom">
          <div class="footer__contacts">
            HALOVIETNAM LTD
            <br>66, Dang Van ngu, Dong Da
            <br>Hanoi, Vietnam
            <br><a href="mailto:contact@halovietnam.com" class="link-item">contact@halovietnam.com</a>
            <br><a href="tel:+84435149182" class="link-item">+844 35149182</a>
          </div>
          <div class="footer__info">
            <div class="footer-links">
              <div class="footer-link"><a class="link-item" href="#">Examples</a></div>
              <div class="footer-link"><a class="link-item" href="#">Shop</a></div>
              <div class="footer-link"><a class="link-item" href="#">Licence</a></div>
            </div>
            <div class="footer-links">
              <div class="footer-link"><a class="link-item" href="#">Contact</a></div>
              <div class="footer-link"><a class="link-item" href="#">About</a></div>
              <div class="footer-link"><a class="link-item" href="#">Privacy</a></div>
              <div class="footer-link"><a class="link-item" href="#">Terms</a></div>
            </div>
            <div class="footer-links">
              <div class="footer-link"><a class="link-item" href="#">Download</a></div>
              <div class="footer-link"><a class="link-item" href="#">Support</a></div>
              <div class="footer-link"><a class="link-item" href="#">Documents</a></div>
            </div>
            <div class="footer-links">
              <div class="footer-link"><a class="link-item" href="#">Media</a></div>
              <div class="footer-link"><a class="link-item" href="#">Blog</a></div>
              <div class="footer-link"><a class="link-item" href="#">Forums</a></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
  export default {

  }

</script>

<style lang="scss">
.footer {
  background-color: #010101;
  padding-top: 82px;
  padding-bottom: 82px;

  &__top {
    display: flex;
    flex-direction: column;
    max-width: 740px;
    margin: 0 auto;

    .title {
      color: #fcdb00;
      font-weight: bold;
      font-size: 32px;
      text-align: center;
    }

    .description {
      font-size: 20px;
      color: #898989;
      text-align: center;
      padding-bottom: 35px;
    }

    .email-field {
      display: flex;
      justify-content: center;


      .text-field {
        outline: none;
        padding: 10px 20px;
        border: none;
        border-radius: 3px;
        max-width: 580px;
        width: 100%;
        transition: all .3s;

        &--error {
          box-shadow: 0px 0px 25px 9px rgba(255, 79, 129, 1);
          transition: all .3s;
        }
      }

      .button {
        background-color: #fcdb00;
        color: #010101;
        border-radius: 3px;
        padding: 13px 36px;
        border: none;
        outline: none;
        text-transform: uppercase;
        font-weight: bold;
        margin-left: 20px;
        cursor: pointer;
        transition: all .3s;

        &--green {
          background-color: #43ff7c;
          transition: all .3s;
        }

        &[disabled] {
          opacity: .6;
          cursor: default;
          transition: all .3s;
        }
      }

      .button-active {
        &:hover {
          filter: brightness(2);
          transition: all .3s;
        }
      }
    }
  }

  &__social {
    display: flex;
    align-self: center;
    padding: 80px 0;
    padding-bottom: 30px;

    .social-icon {
      margin: 0 15px;
      transition: all .3s;

      &:hover {
        filter: brightness(2);
        transition: all .3s;
      }
    }
  }

  .footer-bottom {
    display: flex;
    justify-content: space-between;
    max-width: 840px;
  }

  &__contacts {
    padding-left: 20px;
    padding-right: 125px;
    color: #fff;
  }

  .link-item {
    color: #010101;
    text-decoration: none;
    color: #fff;
    transition: all .3s;

    &:hover {
      color: #fcdb00;
      transition: all .3s;
    }
  }

  &__info {
    display: flex;
    min-width: 530px;
    justify-content: space-between;

    .footer-links {
      color: #fff;
      display: flex;
      flex-direction: column;
    }
  }
}

@media (max-width: 992px) {
    .footer {
        padding-top: 50px;

        &__top {
            .title {
                font-size: 28px;
                padding-bottom: 10px;
            }

            .description {
                font-size: 18px;
                padding-left: 15px;
                padding-right: 15px;
            }
        }

        .footer-bottom {
            flex-direction: column;
            align-items: center;
        }

        &__contacts {
            padding-bottom: 30px;
            text-align: center;
            padding-left: 0;
            padding-right: 0;        
        }

        &__info {
            flex-flow: row wrap;

            .footer-links {
                flex-basis: 50%;

                .footer-link {
                    text-align: center;
                }
            }
        }
    }
}

@media (max-width: 768px) {
    .footer {
        &__top {
            .email-field {
                max-width: 90%;
                width: 100%;
                margin: 0 auto;
            }
        }

        &__info {
            min-width: 0;
        }
    }
}

@media (max-width: 576px) {
    .footer {
        &__info {
            flex-flow: row wrap;

            .footer-links {
                flex-basis: 100%;

                .footer-link {
                    text-align: center;
                }
            }
        }

        &__top {
            .email-field {
                flex-direction: column;
                margin: 0 auto;
                .text-field {
                    margin-bottom: 10px;
                    width: 100%;
                }
                .button {
                    margin-left: 0;
                }
            }
        }

    }
}
</style>