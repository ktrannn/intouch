<template>
  <div>
    <nuxt />
  </div>
</template>

<style lang="scss">
:root {
  --color-pink: #cd3e63;
  --color-teal: #5dc9c1;
  --color-orange: #f2ae44;
  --color-purple: #a769d2;
  --color-light-pink: #fecdda;
  --color-white: #fff;
}

html {
  font-family: "Lato", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 62.5%;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  margin: 0;

  @media (max-width:1024px) {
    padding-bottom: 7rem;
  }
}

h1 {
  font-size: 3.2rem;
}

h2 {
  font-size: 2.4rem;
}

h3 {
  font-size: 2rem;
}

h4 {
  font-size: 1.8rem;
}

h5 {
  font-size: 1.4rem;
}

p {
  font-size: 1.6rem;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 700;
}

.card {
  border-radius: 10px;
  background-color: #fff;
  padding: 2rem;
  margin: 2rem;
  box-shadow: 0 0.4rem 1.2rem rgba(0, 0, 0, 0.2);

  &__title {
    font-weight: 700;
  }

  &__text {
    padding-top: 1rem;
  }
}

.mb-sm {
  margin-bottom: 1.6rem;
}

.mb-xs {
  margin-bottom: 1.2rem;
}

.mb-xxs {
  margin-bottom: 0.8rem;
}

.wrapper {
  margin: 0 auto;
  max-width: 110rem;
  width: 100%;
}
</style>
