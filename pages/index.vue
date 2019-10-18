<template>
  <div class="test">
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
              :controls-text="['<h1 class=test></h1>','<i class=fa-chevron-right></i>']"
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
              @featureModal="featureModal = true"
            />
          </vue-tiny-slider>
        </no-ssr>
      </div>
      <vue-footer/>

      <transition name=fade>
        <div v-if="featureModal" class="about-modal">
          <div class="about-modal__container">
            <div class="about-modal__back-drop" @click="featureModal = false"></div>
            <div class="about-modal__shape"></div>
            <div class="about-modal__content">
              <div class="about-modal__close" @click="featureModal = false"><i class="fas fa-times"></i></div>
              <div class="about-modal__information-container">
                <div class="about-modal__information">
                  <div class="about-modal__title">
                    <img src="~/assets/images/secondary-page-logo.png" alt="">
                    <h2>How Did We Start?</h2>
                  </div>
                  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam natus labore tenetur quibusdam similique deserunt reprehenderit repellendus illo voluptate dignissimos?</p>
                  <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quasi, cumque.</p>
                  <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis voluptatum tempora temporibus iusto sunt id at reprehenderit tempore, sequi voluptatibus, beatae iste harum repudiandae. Iusto reiciendis molestias praesentium tempore magni?</p>
                </div>
                <div class="about-modal__image">
                  <img src="~/assets/images/about-image.png" alt="About Image">
                </div>
              </div>
            </div>
          </div>
        </div>
      </transition>
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
      featureModal: false,
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
    transition: all 0.5s cubic-bezier(.99,.02,.51,1.01);
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

  }

  button:nth-child(1) {
    content: "\f053";
    transform: translateX(4rem);
  }

  button:nth-child(2) {
    font-family: "Font Awesome";
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

.about-modal {
  position: fixed;
  height: 100%;
  top: 0;
  left: 0;
  right: 0;
  top: 0;
  z-index: 100;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 3rem;

  &__container {
    width: 100%;
    height: 80%;
    overflow: scroll;
    background: #fff;
    border-radius: 3px;
    padding: 3rem;

    @media (min-width:1024px) {
      overflow: unset;
      height: auto;
    }
  }

  &__back-drop {
    background: rgba(0,0,0,0.75);
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    z-index: -1;
  }

  &__close {
    font-size: 3rem;
    position: absolute;
    right: -1rem;
    top: -1rem;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    cursor: pointer;
    color: var(--color-pink);
    z-index: 10;
  }

  &__content {
    position: relative;
  }

  &__title {
    display: flex;
    align-items: center;

    img {
      height: 5rem;
      width: 5rem;
      margin-right: 2rem;
    }

    h2 {
      color: var(--color-teal);
    }
  }

  &__information-container {
    display: flex;
    flex-direction: column;

    @media (min-width: 1024px) {
      flex-direction: row;
    }
  }

  &__information {
    flex-basis: 50%;
    padding: 3rem;
  }

  &__image {
    flex-basis: 50%;
    position: relative;
    z-index: 2;
    display: flex;
    justify-content: center;
  }

  &__shape {
    background: linear-gradient(135.34deg, #e87492 0%, #cd3e63 100%);
    position: absolute;
    left: 0;
    right: 0;
    width: 100%;
    bottom: -30%;
    height: 30vh;
    border-radius: 30px 0 0 0;
    transform: skewY(-15deg);

    @media (max-width: 1024px) {
      display: none;
    }
  }
}
</style>
