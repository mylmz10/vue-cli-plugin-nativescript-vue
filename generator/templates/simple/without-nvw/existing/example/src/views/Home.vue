<%_ if (rootOptions.router) { _%>
<template>
  <div class="w-page">
    <div class="w-container">
      <img src="~/assets/logo.png" alt="logo">
      <HelloWorld :msg="msg" />
    </div>
  </div>
</template>
<script>
  // ~ is an alias to /src
  import HelloWorld from 'components/HelloWorld'

  export default {
    name: 'home',
    components: {
      HelloWorld
    },
    data() {
      return {
        msg: 'Mode=' + process.env.TNS_APP_MODE + ' and Platform=' + process.env.TNS_APP_PLATFORM
      }
    },  
  }
</script>
<%_ } _%>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<%_ if (rootOptions.cssPreprocessor !== 'stylus') { _%>
<style scoped<%-
  rootOptions.cssPreprocessor
    ? ` lang="${
        rootOptions.cssPreprocessor === 'sass'
          ? 'scss'
          : rootOptions.cssPreprocessor
      }"`
    : ``
%>>
  img {
    height: 20%;
    width: 20%;
  }
</style>
<%_ } else { _%>
<style scoped lang="stylus">
  img
    height 20%
    width 20%
</style>
<%_ } _%>
