<template>
  <div id="app">
    <link href="https://cdn.jsdelivr.net/npm/animate.css@3.5.1" rel="stylesheet" type="text/css">
    <div id="nav-bar">
      <ul>
        <li>
          <transition
          name="custom-classes-transition"
          enter-active-class="animated fadeInDown"
          leave-active-class="animated fadeOutDown"
          mode="out-in">
            <component v-bind:is="view"></component>
          </transition>
        </li>
        <li v-on:click="goWelcome" class="clickable">
          Welcome
        </li>
        <li v-on:click="goProfile" class="clickable">
          Profile
        </li>
      </ul>
    </div>
    <transition name="component-fade" mode="out-in">
      <component v-bind:is="body_view"></component>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      view: 'v-welcome-logo',
      body_view: 'v-welcome'
    }
  },

  components: {
    'v-welcome-logo': {
      template: '<img src="../src/assets/home.png">'
    },
    'v-profile-logo': {
      template: '<img src="../src/assets/profile.png">'
    },
    'v-welcome': {
      template: '<div id="body_content"> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec id enim gravida, interdum purus vel, faucibus lacus. Nunc interdum efficitur odio, vel eleifend dui porttitor eget. Donec pellentesque blandit arcu, eu condimentum enim maximus eget. In fringilla quam vel orci tincidunt aliquam. Proin finibus tempor sem blandit posuere. Etiam elementum imperdiet turpis non blandit. In sollicitudin nisl ac dapibus consequat.'+
                'Suspendisse pellentesque mi nec justo porttitor semper. Vivamus tincidunt et nibh sit amet tempor. Nunc placerat dui et metus pellentesque, ac faucibus enim facilisis. Suspendisse ex ligula, tempus quis cursus at, consectetur a urna. Etiam gravida porttitor risus, at viverra dui condimentum vel. Nam sagittis lectus mauris, sed sodales massa dapibus vitae. Cras vitae consectetur velit, eget egestas purus. Quisque consectetur cursus libero viverra consequat. Donec posuere nisi'+ 'sed porttitor venenatis. Donec elit magna, pharetra eget est in, laoreet rhoncus urna.' +
                '</div>'
    },
    'v-profile': {
      template: '<div id="body_content"> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec id enim gravida, interdum purus vel, faucibus lacus. Nunc interdum efficitur odio, vel eleifend dui porttitor eget. Donec pellentesque blandit arcu, eu condimentum enim maximus eget. In fringilla quam vel orci tincidunt aliquam. Proin finibus tempor sem blandit posuere. Etiam elementum imperdiet turpis non blandit. In sollicitudin nisl ac dapibus consequat.'+
                'Suspendisse pellentesque mi nec justo porttitor semper. Vivamus tincidunt et nibh sit amet tempor. Nunc placerat dui et metus pellentesque, ac faucibus enim facilisis. Suspendisse ex ligula, tempus quis cursus at, consectetur a urna. Etiam gravida porttitor risus, at viverra dui condimentum vel. Nam sagittis lectus mauris, sed sodales massa dapibus vitae. Cras vitae consectetur velit, eget egestas purus. Quisque consectetur cursus libero viverra consequat. Donec posuere nisi'+ 'sed porttitor venenatis. Donec elit magna, pharetra eget est in, laoreet rhoncus urna.' +
                '</div>'
    }


  },

  methods: {
    goWelcome: function(){
      this.view = 'v-welcome-logo',
      this.body_view = 'v-welcome'
    },

    goProfile: function(){
      this.view = 'v-profile-logo',
      this.body_view = 'v-profile'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding-left: 200px;
  padding-right: 200px;
  margin-top: 10px;
}

#nav-bar{
  margin: 0 auto;
  width: 70%;
  padding-top: 10px;
}

#body_content {
  padding-top: 100px;
}

.component-fade-enter-active, .component-fade-leave-active {
  transition: opacity .5s ease;
}
.component-fade-enter, .component-fade-leave-to
/* .component-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.clickable {
  cursor: pointer;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
  min-width: 100px;
  max-height: 22px;
}

li img {
  width:22px;
  height: 22px;
}

a {
  color: #42b983;
}
</style>
