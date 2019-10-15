<template>
  <div>
    <div class="homepage-hero">
      <div class="wrapper">
        <div class="header__buttons">
          <header-logo></header-logo>
          <nav-buttons class="nav-buttons"></nav-buttons>
        </div>
        <div>
          <div>
            <h1 class="homepage-title">Dedicated to the Improvement of Your Body</h1>
            <div class="services-container">
              <div
                v-for="(service, id) in services"
                :key="id"
                class="service"
                :class="'service-' + id"
              >
                <service-card :services="service" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="wrapper">
      <div class="secondary-cta">
        <h2>Multidisciplinary Rehab Facility Offering State of the Art Equipment</h2>
        <p>Email Us For Any Enquires: info@tclifestyle.ca</p>
      </div>
    </div>

    <div class="footer-wrapper">
      <div class="wrapper">
        <div class="featured-container">
          <h2 class="mb-md">Featured Equipment</h2>
        </div>
        <no-ssr>
          <vue-tiny-slider
              :items="1"
              :controls-text="['<','>']"
              :mouse-drag="true"
              :touch="true"
              :autoplay="true"
              :speed="650"
              :auto-play-timeout="3000"
          >
            <feature-card
              v-for="(features, id) in features"
              :key="id"
              :features="features"
              class="feature-card"
              :class="'feature-card-' + id"
            />
          </vue-tiny-slider>
        </no-ssr>
      </div>
      <vue-footer/>
    </div>
  </div>
</template>

<script>
import NavButtons from '~/components/NavButtons.vue';
import HeaderLogo from '~/components/HeaderLogo.vue';
import ServiceCard from '~/components/ServiceCard.vue';
import FeatureCard from '~/components/FeatureCard.vue';
import VueFooter from '~/components/Footer.vue';

export default {
  components: {
    ServiceCard,
    FeatureCard,
    VueFooter,
    NavButtons,
    HeaderLogo,
  },
  data() {
    return {
      isMobile: false,
      services: [
        {
          title: 'Physiotherapy',
          link: '/physiotherapy',
        },
        {
          title: 'Occupation Therapist',
          link: '/occupationaltherapy',
        },
        {
          title: 'Registered Massage Therapist',
          link: '/rmt',
        },
        {
          title: 'Speech Language Pathologist',
          link: '/speechlanguagetherapy',
        },
      ],
      features: [
        {
          title: 'Featured Equipment 1',
        },
        {
          title: 'Featured Equipment 2',
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.homepage-hero {
  background-image: url('../assets/images/hero-image.jpg');
  background-size: cover;
  background-position: center top;
  background-repeat: no-repeat;
  min-height: 60vh;
  display: flex;
  justify-content: space-between;
  flex-direction: column;

  .services-button {
    display: none !important;
  }
}

.homepage-title {
  padding: 0 3rem;
  width: 80%;
  margin-top: 20rem;
  font-size: 3rem;

  @media (min-width: 1024px) {
    font-size: 6rem;
    margin-top: 30rem;
    width: 70%;
  }
}

.container {
  margin: 0 auto;
  min-height: 100vh;
}

.services-container {
  padding: 3rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.service {
  display: flex;
  justify-content: flex-end;
  flex-direction: column;
  flex-basis: 100%;
  height: 25rem;
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;

  &::after {
    content: "";
    position: absolute;
    width: 100%;
    bottom: 0;
    left: 0;
    right: 0;
    height: 0.5rem;
    transition: all 0.5s ease-in;
    opacity: 0.85;
  }

  &:hover {
    &::after {
      height: 100%;
    }
  }

  &-0 {
    background-image: url("../assets/images/service-1.jpg");

    &::after {
      background-color: var(--color-pink);
    }
  }

  &-1 {
    background-image: url("../assets/images/service-2.jpg");

    &::after {
      background-color: var(--color-teal);
    }
  }

  &-2 {
    background-image: url("../assets/images/service-3.jpg");

    &::after {
      background-color: var(--color-orange);
    }
  }

  &-3 {
    background-image: url("../assets/images/service-4.jpg");

    &::after {
      background-color: var(--color-purple);
    }
  }

  @media (min-width: 420px) {
    flex-basis: 50%;
  }

  @media (min-width: 768px) {
    flex-basis: 25%;
    height: 36rem;
  }

  &__title {
    padding: 2rem;
    margin: 0;
  }

  a {
    height: 100%;
    display: flex;
    align-items: flex-end;
    position: relative;
    z-index: 1;
    color: var(--color-white);
    text-decoration: none;
  }
}

.secondary-cta {
  padding: 3rem;
  margin: auto;

  @media (min-width: 768px) {
    width: 50%;
  }

  h2 {
    color: var(--color-orange);
    line-height: 1.75;
    margin-bottom: 3rem;
  }

  p {
    color: #808080;
  }
}

.featured-container {
  padding: 0 3rem;

  > h2 {
    color: var(--color-teal);
  }
}

.feature-card {
  height: 26rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  cursor: pointer;
  width: 100%;
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;

  &::after {
    content: "";
    background: linear-gradient(to bottom, rgba(59, 59, 59, 0), rgba(59, 59, 59, 0.01) 9%, rgba(59, 59, 59, 0.05) 17%, rgba(59, 59, 59, 0.1) 24%, rgba(59, 59, 59, 0.17) 31%, rgba(59, 59, 59, 0.26) 37%, rgba(59, 59, 59, 0.35) 44%, rgba(59, 59, 59, 0.44) 50%, rgba(59, 59, 59, 0.53) 56%, rgba(59, 59, 59, 0.62) 63%, rgba(59, 59, 59, 0.71) 69%, rgba(59, 59, 59, 0.78) 76%, rgba(59, 59, 59, 0.83) 83%, rgba(59, 59, 59, 0.87) 91%, rgba(59, 59, 59, 0.88));
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }

  @media (min-width: 768px) {
    height: 50rem;
  }

  &__title {
    margin: 0;
    color: var(--color-white);
    z-index: 1;
  }

  p {
    color: var(--color-teal);
    font-weight: bold;
    z-index: 1;
  }

  &-0 {
    background-image: url("../assets/images/featured-1.jpg");
  }

  &-1 {
    background-image: url("../assets/images/featured-1.jpg");
  }
}

.tns-ovh {
  padding: 3rem;
}

.tns-outer {
  z-index: 2;
  position: relative;

  > button {
    display: none;
  }
}

.tns-controls {
  position: absolute;
  bottom: 5rem;
  z-index: 1;
  display: flex;
  justify-content: space-between;
  width: 100%;
  right: 0;
  left: 0;
  outline: none;

  @media (max-width: 768px) {
    display: none;
  }

  button {
    width: 5rem;
    height: 5rem;
    border-radius: 50%;
    border: none;
    background-color: var(--color-teal);
    outline: none;
    cursor: pointer;
    font-family: 'Font Awesome 5';

  }

  button:nth-child(1) {
    content: "\f053";
    transform: translateX(4rem);
  }

  button:nth-child(2) {
    content: "\f054";
    transform: translateX(-4rem);
  }
}

.tns-slider {
  display: flex;
}

.tns-inner {
  overflow: hidden;
}

.footer-wrapper {
  position: relative;
  overflow: hidden;
}
</style>
