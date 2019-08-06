<template>
  <footer class="footer">
    <div class="container">
      <div class="row flex-column">
        <div class="footer__top">
          <div class="title">{{ footerItems.title }}</div>
          <div class="description">{{ footerItems.description }}</div>
          <form class="email-field" @submit.prevent>
            <label for="email" @submit.prevent></label>
            <input 
              id="email" 
              type="email" 
              :placeholder="inputPlaceholder"
              class="text-field"
              :class="{'text-field--error' : $v.email.$error && (!$v.email.required || !$v.email.email)}"
              :disabled="isEmailSent"
              @input="$v.email.$touch()"
              v-model="email"
            >
            <button 
              type="submit"
              class="button"
              :class="{'button--green' : isEmailSent}"
              :disabled="!$v.email.required || !$v.email.email"
              @click="submitForm"
            >
              {{ btnName }}
            </button>
          </form>
        </div>
        <div class="footer__social">
          <a 
            v-for="(social, index) in footerItems.imgURLs"
            :key="index"
            :href="social.linkURL"
          ><img :src="getDir(social.imgURL)" :alt="social.alt" class="social-icon"></a>
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
            <div 
              class="footer-links"
              v-for="(column, index) in footerItems.links"
              :key="index"
            >
              <div 
                class="footer-link"
                v-for="linkItem of column"
                :key="linkItem.id"
              >
                <a class="link-item" :href="linkItem.url">{{ linkItem.name }}  </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import { required, email } from "vuelidate/lib/validators";

export default {
  data() {
    return {
      footerItems: [],
      resource: null,
      email: '',
      btnName: 'Submit',
      isEmailSent: false,
      inputPlaceholder: 'Enter your email to update'
    }
  },
  created() {
    this.resource = this.$resource('footer')
  },
  mounted() {
    this.loadFooter()
  },
  methods: {
    loadFooter() {
      this.resource.get().then(response => response.json())
        .then(footer => this.footerItems = footer)
    },
    getDir(img) {
      return require('../assets/' + img)
    },
    submitForm() {
      Email.send({
        Host: 'mail.adm.tools',
        Username: 'products@vtlxn.xyz',
        Password: 'l70Yo02vIVAd',
        To: this.email,
        From: 'products@vtlxn.xyz',
        Subject: 'Test site',
        Body: 'Привіт, це перевірка тестового завдання, яке зробив Віталій Бережний.'
      });
      this.email = ''
      this.btnName = 'Thanks!'
      this.$v.email.$reset()
      this.isEmailSent = true
      this.inputPlaceholder = 'Email sent to your inbox'
    }
  },
  validations: {
  email: {
    required,
    email
  }
}
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