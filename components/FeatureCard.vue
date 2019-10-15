<template>
  <div>
    <h3 class="feature-card__title">{{ features.title }}</h3>
    <p>Learn More</p>
  </div>
</template>

<script>
export default {
  props: {
    features: Object,
  },
};
</script>
