<!-- eslint-disable --> 
<template>
  <div class="list-wrapper">
    <form @submit.prevent="formSubmitted" class="list__form">
      <p class="list__title">فرم استخدام</p>
      <BaseInput
        v-model="firstName"
        :label="formLabelAndPlaceholder.firstName"
        type="text"
        :placeHolder="formLabelAndPlaceholder.firstName"
      />

      <BaseInput
        v-model="lastName"
        :label="formLabelAndPlaceholder.lastName"
        type="text"
        :placeHolder="formLabelAndPlaceholder.lastName"
      />

      <BaseInput
        v-model="age"
        label="سن"
        type="number"
      />

      <button class="list__button">تایید</button>
    </form>
  </div>
</template>

<script>
/* eslint-disable-next-line */
/* eslint-disable */
import { ref } from "@vue/reactivity";
import BaseInput from "./components/BaseInput.vue";
export default {
  name: "App",
  components: {
    BaseInput,
  },
  setup() {
    const firstName = ref(null);
    const lastName = ref(null);
    const age = ref('')
    const formLabelAndPlaceholder = ref({
      firstName: "نام",
      lastName: "نام خانوادگی",
    });

    const formSubmitted = () => {
      console.log({ firstName: firstName.value, lastName: lastName.value , userAge : age.value });
    };

    return {
      firstName,
      lastName,
      formLabelAndPlaceholder,
      age,
      formSubmitted,
    };
  },
};
</script>

<style lang="scss">
@import "./assets/styles/global.css";
@font-face {
  font-family: "IranSans";
  src: url("./assets/fonts/iransans.ttf");
}

.list-wrapper {
  width: 100%;
  height: 100vh;
  background-color: #f7f6f5;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.list__title {
  color: #222;
  font-size: 30px;
  text-align: center;
  margin-bottom: 10px;
}

.list__form {
  width: 500px;
  height: 500px;
  background-color: #fff;
  display: flex;
  flex-direction: column;
  padding: 15px 10px;
  border-radius: 10px;
  box-shadow: 0 0 20px 1px rgba(0, 0, 0, 0.07);
}
.list__button {
  margin: 20px 20px 0;
  height: 30px;
  border-radius: 5px;
  color: #000;
  background: #c69e4e;
}
</style>
