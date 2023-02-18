<script setup>
import { reactive } from "vue";

import BaseForm from "./components/BaseForm.vue";

const formFields = reactive({
  email: "",
  password: "",
  check: false,
});
</script>

<template>
  <div class="container">
    <section class="section">
      <div class="columns">
        <div class="column">
          <h1 class="title">Login</h1>
          <BaseForm v-model:formFields="formFields" />
        </div>

        <div class="column">
          <article class="message is-small">
            <div class="message-header">
              <p>Form props</p>
            </div>
            <div class="message-body">
              <pre class="has-text-left content">
                {{ formFields }}
              </pre>
            </div>
          </article>
        </div>
      </div>
    </section>
  </div>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
</style>
