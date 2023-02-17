<script setup>
import { computed } from "vue";

const emit = defineEmits(['update:email', 'update:password', 'update:check']);

const props = defineProps({
  email: {
    type: String,
    required: true,
  },
  password: {
    type: String,
    required: true
  },
  check: {
    type: Boolean,
    required: true
  }
});

 const formEmail = computed({
    get() {
      return props.email;
    },
    set(newValue){
      emit('update:email', newValue);
    }
 });

 const formPassword = computed({
    get() {
      return props.password;
    },
    set(newValue) {
      emit("update:password", newValue);
    },
 })

 const formCheck = computed({
    get() {
      return props.check;
    },
    set(newValue) {
      emit("update:check", newValue);
    },
 })


 const handleSubmit = () => {
  console.log("Submit")
 }

</script>


<template>
  <form @submit.prevent="handleSubmit">
    <div class="field">
      <p class="control">
        <input class="input" type="email" placeholder="Email" v-model="formEmail" maxlength="30" required>
      </p>
    </div>
    <div class="field">
      <p class="control">
        <input class="input" type="password" placeholder="Password" v-model="formPassword" maxlength="16" required>
      </p>
    </div>
    <div class="field">
      <label class="checkbox">
        <input type="checkbox" v-model="formCheck">
        Remember me
      </label>
    </div>
    <div class="field">
      <p class="control">
        <button class="button is-link">
          Login
        </button>
      </p>
    </div>
  </form>
</template>
