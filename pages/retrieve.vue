<template>
  <main class="c-retrieve container">
    <h2>
      Enter your email and we’ll send your tickets right away!
    </h2>
    <div>
      <form
        v-if="!success"
        class="c-retrieve__request"
        @submit.prevent="success = true"
      >
        <label for="email" class="c-form__label">Email address</label>
        <input
          type="email"
          name="email"
          id="email"
          class="c-form__input"
          required
          v-model="email"
        />
        <button type="submit" class="c-button c-button--yellow">
          CONFIRM AND SEND TICKET
        </button>
      </form>
      <div v-else class="c-retrieve__success">
        <check-icon />
        <p class="c-success__message">
          Your tickets have been confirmed and sent to your email address at
          <span>{{ email }}</span>
        </p>
        <nuxt-link to="/">
          <button type="button" class="c-button c-button--yellow">
            Buy more tickets
          </button>
        </nuxt-link>
      </div>
    </div>
    <div class="c-lines"></div>
  </main>
</template>

<script>
import CheckIcon from "~/components/CheckIcon.vue";
export default {
  components: { CheckIcon },
  data() {
    return {
      email: "",
      success: false
    };
  }
};
</script>

<style lang="scss" scoped></style>
