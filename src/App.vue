<template>
  <div id="app">
    <div class="lala"></div>
    <headerComponent></headerComponent>
    <mainComponent></mainComponent>
    <featuresComponent></featuresComponent>
    <footerComponent></footerComponent>
  </div>
</template>

<script>
  import headerComponent from "./components/header";
  import mainComponent from "./components/main";
  import featuresComponent from "./components/features";
  import footerComponent from "./components/footer";

  export default {
    name: 'app',
    components: {
      headerComponent,
      mainComponent,
      featuresComponent,
      footerComponent
    }
  }

</script>

<style lang="scss">

  body {
      font-family: 'PT Sans';
      min-width: 360px !important;
  }

  @media (min-width: 1200px) {
    .container {
        max-width: 960px !important;
    }
}
</style>
