<template>
  <div>
    <div id="componente">
      Inside the component 1:
      <input
        :type="type"
        :name="modelValue"
        :placeholder="placeholder"
        @input="$emit('update:modelValue', $event.target.value)"
      />
      {{ modelValue }}
    </div>
  </div>
</template>

<script>
export default {
  // props: ["email", "modelValue", "aboutus"],
  props: {
    placeholder: String,
    email: "",
    name: "",
    type: {
      default: "text",
    },
    modelValue: {
      type: String,
      required: true,
      default: "Text!!",
    },
  },
};
</script>

<style scoped>
#componente {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 50%;
  padding: 40px;
  align-items: center;
  background: #333;
  box-sizing: border-box;
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.6);
  border-radius: 50px;
  align-content: center;
  margin-top: 50px;
  margin-bottom: 50px;
  color: white;
}

input {
  background: #04aa6d;
  color: white;
}
</style>
