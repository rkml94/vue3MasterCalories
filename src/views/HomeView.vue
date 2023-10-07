<template>
  <div class="home">
    <SignInVue/>
  </div>
</template>

<script>
// @ is an alias to /src
import SignInVue from '@/components/SignIn.vue'

export default {
  name: 'HomeView',
  components: {
    SignInVue
  }
}
</script>
