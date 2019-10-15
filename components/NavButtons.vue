<template>
  <header v-if="!isMobile">
    <nuxt-link to="career" class="about-button" tag="div">Careers</nuxt-link>
    <div class="about-button" @click="openAbout">About Us</div>
    <nuxt-link to="PhysioTherapy" class="about-button services-button" tag="div">Services</nuxt-link>
    <transition name=fade>
      <div v-if="aboutModal" class="about-modal">
        <div class="about-modal__container">
          <div class="about-modal__back-drop" @click="aboutModal = false"></div>
          <div class="about-modal__shape"></div>
          <div class="about-modal__content">
            <div class="about-modal__close" @click="aboutModal = false"><i class="fas fa-times"></i></div>
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
  </header>
</template>

<script>
export default {
  data() {
    return {
      aboutModal: false,
      isMobile: false,
    };
  },
  methods: {
    openAbout() {
      this.aboutModal = true;
    },
    checkMobile() {
      window.matchMedia('screen and ( max-width: 768px )').matches
        ? (this.isMobile = true)
        : (this.isMobile = false);
    },
  },
  mounted() {
    this.checkMobile();
  },
};

</script>

<style lang="scss" scoped>

.about-button {
  background-color: transparent;
  border: 2px solid #5dc9c1;
  color: #5dc9c1;
  font-size: 2.2rem;
  font-weight: bold;
  border-radius: 5rem;
  cursor: pointer;
  width: 18rem;
  height: 4rem;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease-in-out;

  &:hover {
    background-color: #5dc9c1;
    color: white;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
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
