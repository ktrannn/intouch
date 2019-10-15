<template>
  <nuxt-link :to="services.link">
    <div>
      <h3 class="service__title">
        {{ services.title }}
      </h3>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    services: Object,
  },
};
</script>
