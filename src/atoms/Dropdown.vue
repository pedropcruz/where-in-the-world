<template>
  <div class="control">
    <div
      :class="`dropdown ${isActive ? 'is-active' : ''}`"
      @click="handleClick"
    >
      <div class="dropdown-trigger">
        <button
          class="button"
          aria-haspopup="true"
          aria-controls="dropdown-menu"
        >
          <span>Filter by Region</span>
          <span class="icon is-small">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </button>
      </div>
      <div class="dropdown-menu" id="dropdown-menu" role="menu">
        <div class="dropdown-content">
          <a href="#" class="dropdown-item">
            Africa
          </a>
          <a class="dropdown-item">
            America
          </a>
          <a href="#" class="dropdown-item">
            Asia
          </a>
          <a href="#" class="dropdown-item">
            Europe
          </a>
          <a href="#" class="dropdown-item">
            Oceania
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false
    };
  },
  methods: {
    handleClick(e) {
      this.isActive = !this.isActive;
      e.preventDefault();
    }
  }
};
</script>
