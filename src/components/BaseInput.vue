<!--  eslint-disable  -->
<!--  eslint-disable-next-line  -->
<template>
  <div class="input-wrapper">
    <label class="input__label">{{ label }}</label>
    <input
      class="input__field"
      :value="modelValue"
      :type="type"
      :placeholder="placeHolder"
      @input="(e) => $emit('update:modelValue', e.target.value)"
    />
  </div>
</template>
<script>
/* eslint-disable-next-line */
/* eslint-disable */
export default {
  name: "CustomInput",
  props: {
    modelValue: [Number, String],
    label: {
      type: String,
      default: "این یک لیبل میباشد",
    },
    type: String,
    placeHolder : String
  },
};
</script>

<style scoped lang="scss">
.input-wrapper {
  display: flex;
  flex-direction: column;
  margin: 0 20px;
  .input__label{
     font-size: 18px;
     color: #555;
     margin-bottom: 5px;
  }
  .input__field{
     border-radius: 3px;
     height: 30px;
     padding: 4px 10px 4px 20px;
  }
}
</style>