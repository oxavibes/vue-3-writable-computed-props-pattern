<script setup>
import { computed } from "vue";

const emit = defineEmits(["update:formFields"]);

const props = defineProps({
  formFields: {
    type: Object,
    required: true,
  },
});

const form = computed({
  get() {
    return props.formFields;
  },
  set(newValue) {
    emit("update:formFields", newValue);
  },
});

const handleSubmit = () => {
  console.log("Submit");
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <div class="field">
      <p class="control">
        <input class="input" type="email" placeholder="Email" v-model="form.email" maxlength="30" required />
      </p>
    </div>
    <div class="field">
      <p class="control">
        <input class="input" type="password" placeholder="Password" v-model="form.password" maxlength="16" required />
      </p>
    </div>
    <div class="field">
      <label class="checkbox">
        <input type="checkbox" v-model="form.check" />
        Remember me
      </label>
    </div>
    <div class="field">
      <p class="control">
        <button class="button is-link">Login</button>
      </p>
    </div>
  </form>
</template>
