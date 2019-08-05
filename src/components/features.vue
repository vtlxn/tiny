<template>
  <section class="features">
    <div class="container">
      <div class="row d-flex flex-column">
        <div class="features__title">
          Tinyone features
        </div>
        <div class="features__decription">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique
          bibendum. Donec rutrum sed sem quis venenatis.
        </div>
        <div class="features__facts">
          <div class="fact">
            <div class="fact-img">
              <img class="fact-icon" src="../assets/icon-font-1.png" alt="">
            </div>
            <div class="fact-text">
              <div class="title">Fully Responsive</div>
              <div class="decription">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Praesent vitae eros eget tellus tristique bibendum.</div>
            </div>
          </div>
          <div class="fact">
            <div class="fact-img">
              <img class="fact-icon" src="../assets/icon-font-2.png" alt="">
            </div>
            <div class="fact-text">
              <div class="title">HTML3 &amp; CSS3</div>
              <div class="decription">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Praesent vitae eros eget tellus tristique bibendum.</div>
            </div>
          </div>
          <div class="fact">
            <div class="fact-img">
              <img class="fact-icon" src="../assets/icon-font-3.png" alt="">
            </div>
            <div class="fact-text">
              <div class="title">Fully Layered PSD</div>
              <div class="decription">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Praesent vitae eros eget tellus tristique bibendum.</div>
            </div>
          </div>
          <div class="fact">
            <div class="fact-img">
              <img class="fact-icon" src="../assets/icon-font-4.png" alt="">
            </div>
            <div class="fact-text">
              <div class="title">Email Template</div>
              <div class="decription">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Praesent vitae eros eget tellus tristique bibendum.</div>
            </div>
          </div>
          <div class="fact">
            <div class="fact-img">
              <img class="fact-icon" src="../assets/icon-font-5.png" alt="">
            </div>
            <div class="fact-text">
              <div class="title">Font Awesome Icons</div>
              <div class="decription">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Praesent vitae eros eget tellus tristique bibendum.</div>
            </div>
          </div>
          <div class="fact">
            <div class="fact-img">
              <img class="fact-icon" src="../assets/icon-font-6.png" alt="">
            </div>
            <div class="fact-text">
              <div class="title">Free to download</div>
              <div class="decription">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Praesent vitae eros eget tellus tristique bibendum.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  export default {

  }

</script>

<style lang="scss">
  .features {
    padding-top: 105px;

    &__title {
        font-size: 32px;
        font-weight: bold;
        color: #010101;
        text-align: center;
    }

    &__decription {
        font-size: 20px;
        color: #313841;
        text-align: center;
        align-self: center;
        max-width: 800px;
    }

    &__facts {
        padding-top: 60px;
        display: flex;
        flex-flow: row wrap;
        align-items: center;

        .fact {
            display: flex;
            min-width: 300px;
            flex-basis: 30%;
            margin: 20px 10px 45px 10px;

            .fact-img {
                display: flex;
                justify-content: center;
                align-items: flex-start;
                min-width: 60px;

                .fact-icon {
                    padding-top: 4px;
                }
            }

            .fact-text {
                padding-left: 20px;

                .title {
                    font-size: 22px;
                    color: #010101;
                }

                .decription {
                    font-size: 16px;
                    color: #898989;
                }
            }
        }
    }
}

@media (max-width: 768px) {
  .features {
    &__title {
      font-size: 30px;
    }

    &__decription {
      font-size: 18px;
      padding-top: 20px;
      padding-left: 10px;
      padding-right: 10px;
    }

    &__facts {
      align-items: center;
      justify-content: center;
    }
  }
}
</style>
