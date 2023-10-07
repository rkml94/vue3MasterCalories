<template>
<v-sheet
    border="md"
    class="pa-6 text-white mx-auto"
    color="#141518"
    height="619px"
  >
    <v-card class="mx-auto px-6 py-8" max-width="344">
      <v-form
        v-model="form"
        @submit.prevent="onSubmit"
      >
        <v-text-field
          v-model="email"
          :readonly="loading"
          :rules="[required]"
          class="mb-2"
          clearable
          label="Email"
        ></v-text-field>

       <v-text-field
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        placeholder="Enter your password"
        prepend-inner-icon="mdi-lock-outline"
        @click:append-inner="visible = !visible"
      ></v-text-field>

        <br>
        <v-btn
          :disabled="!form"
          :loading="loading"
          block
          color="success"
          size="large"
          type="submit"
          variant="elevated"
        >
          Sign In
        </v-btn>
      </v-form>
    </v-card>
  </v-sheet>
</template>
<script>
  export default {
    data: () => ({
      form: false,
      email: null,
      password: null,
      loading: false,
      visible: false,
    }),

    methods: {
      onSubmit () {
        if (!this.form) return
        this.loading = true
        this.$router.push('/data-table');
        
        setTimeout(() => (this.loading = false), 2000)
      },
      required (v) {
        return !!v || 'Field is required'
      },
    },
  }
</script>