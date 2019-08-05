<template>
  <header class="header">
    <div class="container">
      <div class="top-menu row justify-content-between align-items-center">
        <div class="logo col-4 d-flex">
          <img src="../assets/logo.png" class="logo__img">
          <div class="logo__text">tinyone</div>
        </div>
        <nav class="navigation col-5 d-lg-block d-none">
          <ul class="navigation-items d-flex justify-content-between">
            <li 
              v-for="navItem of navItems"
              class="navigation-item"
              :key="navItem.id"
            >
              <a class="link link-item" href="#">{{ navItem.title }}</a>
            </li>
          </ul>
        </nav>
        <button 
          id="menu-btn" 
          @click="menuVisible = !menuVisible" 
          :class="{'is-active' : menuVisible}" 
          class="menu-btn-mobile d-lg-none hamburger hamburger--elastic" 
          type="button"
        >
          <span class="hamburger-box nav-icon">
            <span class="hamburger-inner"></span>
          </span>
        </button>
        <div :class="{hidden : !menuVisible}" class="menu-mobile d-lg-none">
          <ul class="menu-mobile__items navigation-items">            
            <li 
              v-for="navItem of navItems"
              class="link-mobile navigation-item"
              :key="navItem.id"
            >
              <a class="link link-item" href="#">{{ navItem.title }}</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
  export default {
      data() {
          return {
            menuVisible: false,
            navItems: [],
            resource: null
          }
      },
      created() {
        this.resource = this.$resource('navitems')
      },
      mounted() {
        this.loadNavItems()
      },
      methods: {
        loadNavItems() {
          this.resource.get().then(response => response.json())
            .then(navitems => this.navItems = navitems)
        }
    }
  }

</script>

<style lang="scss">
  .header {
    position: relative;
    background-color: #fcdb00;
    padding: 60px 0;

    .top-menu {
      .logo {
        cursor: pointer;
        user-select: none;

        &__img {
          padding-right: 10px;
          pointer-events: none;
        }

        &__text {
          font-size: 30px;
          font-weight: bold;
          color: #010101;
        }
      }

      .navigation {
        padding-left: 32px;
        padding-top: 10px;
      }

      .navigation-items {
        list-style-type: none;
        margin: 0;
        padding: 0;

        .link-item {
          font-size: 22px;
          font-weight: bold;
          color: #010101;
          text-decoration: none;
          transition: all .3s;

          &:hover {
            color: #fff;
            transition: all .3s;
          }
        }
      }

      .menu-btn-mobile {
        position: absolute;
        padding-top: 24px;
        right: 0;
        cursor: pointer;
        position: relative;
        outline: none;
      }

      .hidden {
        display: none;
      }

      .menu-mobile {
        position: absolute;
        top: 120%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 100%;
        background-color: opacify(rgba(#fcdb00, 0.5), 0.3);
        z-index: 10;
        user-select: none;

        &__items {
          display: flex;
          flex-direction: column;

          .link-mobile {
            text-align: center;
            padding: 10px 0;
            transition: all .5s;

            &:hover {
              background-color: lighten(#fcdb00, 15%);
              transition: all .5s;
            }
          }
        }
      }
    }
  }

  @media (max-width: 992px) {
    .header {
      position: fixed;
      width: 100%;
      padding: 0;
      background-color: opacify(rgba(#fcdb00, 0.5), 0.3);
      z-index: 100;

      .top-menu {
        .menu-mobile {
          margin-top: 67px;
        }
      }
    }
  }

</style>
