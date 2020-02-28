<template>
  <nav class="navbar has-shadow" role="navigation" aria-label="main navigation">
    <div class="container">
      <div class="navbar-brand">
        <router-link
          class="navbar-item has-text-dark has-text-weight-bold is-size-4"
          to="/"
          >Where in the world?</router-link
        >
      </div>
      <div class="navbar-menu">
        <div class="navbar-end">
          <div class="buttons">
            <Button />
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import Button from "@/atoms/Button.vue";

export default {
  components: { Button }
};
</script>
