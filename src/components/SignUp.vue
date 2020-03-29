<template>
  <div id="sign-up">
    <div class="sign-up__form">
      <h1 class="sign-up__form--title">Sign up</h1>
      <v-form class="sign-up__form--form" lazy-validation>
        <v-text-field v-model="name" label="Name" required></v-text-field>
        <v-text-field
          v-model="email"
          label="Email Address"
          required
        ></v-text-field>
        <v-text-field
          :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
          :rules="[rules.required, rules.min]"
          :type="show ? 'text' : 'password'"
          label="Password"
          hint="At least 8 characters"
          @click:append="show = !show"
        ></v-text-field>
      </v-form>
      <!-- <button class="sign-up__form--btn" rounded @click="submit">
        Create Account
      </button> -->
      <v-btn fab class="sign-up__form--btn" elevation="0" rounded @click="submit">
        Create Account
      </v-btn>
    </div>
    <div class="sign-up__img">
      <v-img src="../assets/CoffeeSignUpPage.jpg" class="sign-up__img--image">
      </v-img>
      <h3 class="sign-up__img--title">
        Buy Me A <span>Coffee</span> is a beautiful way for creators to accept
        one-time and monthly support from their fans.
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignUp",
  data: () => ({
    name: "",
    password: "",
    email: "",
    show: false,
    rules: {
      required: value => !!value || "Required.",
      min: v => v.length >= 8 || "Min 8 characters"
    }
  }),
  methods: {
    submit() {
      this.$v.$touch();
    }
  }
};
</script>

<style lang="sass" scoped>
@import url('https://fonts.googleapis.com/css?family=Muli:200,400&display=swap')
$white: #ffffff
$black: #000000
$brown: #331900
#sign-up
  width: 100%
  height: 100%
  display: flex
  flex-direction: row
  font-family: 'Muli', sans-serif
  .sign-up__img
    width: 50%
    display: flex
    align-items: center
    &--image
      width: 100%
      height: 100%
      object-fit: cover
    &--title
      position: absolute
      color: $black
      font-size: 35px
      font-weight: 100
      padding: 2rem 2rem 11rem
      width: 30rem
      >span
        color: $brown
        font-weight: 500


  .sign-up__form
      width: 50%
      display: flex
      flex-direction: column
      justify-content: center
      align-items: center
      &--title
        font-size: 35px
        font-weight: 100
        padding-right: 35%
        padding-bottom: 20px
      &--form
        width: 50%
        margin: 20px 0px
      &--btn
        width: 16rem
        height: 50px
        font-size: 16px
        font-weight: 200
        color: $white
        background-color: $black
        text-transform: none
        letter-spacing: 0
</style>
