<template>
  <select
    class="form-floating form-select"
    v-model="selectedOption"
    @change="emitOption"
  >
    <option value="">{{ placeholder || "Select an option" }}</option>
    <option
      v-for="option in options"
      :key="option.value || option"
      :value="option.value || option"
    >
      {{ option.label || option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "SelectFilter",
  data() {
    return {
      selectedOption: "",
    };
  },
  props: {
    placeholder: String,
    options: Array,
  },
  methods: {
    emitOption() {
      this.$emit("option-change", this.selectedOption);
    },
  },
};
</script>

