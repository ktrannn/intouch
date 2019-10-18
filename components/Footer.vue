<template>
  <div class="footer">
    <div class="footer__shape"></div>
    <div class="footer__info-container">
      <div class="footer-item-container">
        <div class="footer-item">
          <div class="footer-icon footer-icon--orange">
            <i class="fas fa-phone-alt"></i>
          </div>
          <div class="footer-item__info">
            <p class="footer-item__text">Schedule An Appointment Or Call For More Info</p>
            <p class="footer-item__link">604-423-4878</p>
          </div>
        </div>
        <div class="footer-item">
          <div class="footer-icon footer-icon--orange">
            <i class="fas fa-map-marker-alt"></i>
          </div>
          <div class="footer-item__info">
            <p class="footer-item__text">591 Cardero Street, CA, Vancouver</p>
          </div>
        </div>
        <div class="footer-item">
          <div class="footer-icon footer-icon--orange">
            <i class="fas fa-envelope"></i>
          </div>
          <div class="footer-item__info">
            <p class="footer-item__text">Schedule An Appointment Or Call For More Info</p>
            <p class="footer-item__link">604-423-4878</p>
          </div>
        </div>
      </div>
      <div class="footer-iframe">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2602.2254270646395!2d-123.13238098431015!3d49.291072679332224!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x54867186237fc2df%3A0x563cd3ef05fde364!2s591%20Cardero%20St%2C%20Vancouver%2C%20BC%20V6G%203L3!5e0!3m2!1sen!2sca!4v1570831559293!5m2!1sen!2sca" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
      </div>
    </div>
    <p class="copy-right">Copyright 2019, TC Lifestyle. Website by Jarell Alvarez</p>
    <div class="mobile-nav">
      <div>
        <div class="mobile-nav__item">
          <nuxt-link to="/">
            <img src="~/assets/images/secondary-page-logo.png" alt />
          </nuxt-link>
        </div>
      </div>
      <div>
        <div class="mobile-nav__item">
          <div class="footer-icon footer-icon--teal">
            <i class="fas fa-phone-alt"></i>
          </div>
          <span>Call Us</span>
        </div>
      </div>
      <div>
        <div class="mobile-nav__item">
          <div class="footer-icon footer-icon--teal">
            <i class="fas fa-map-marker-alt"></i>
          </div>
          <span>Location</span>
        </div>
      </div>
      <div>
        <div class="mobile-nav__item" @click="toggleMenu">
          <div class="footer-icon footer-icon--teal">
            <i class="fas fa-bars"></i>
          </div>
          <span>Menu</span>
          <transition name="fade">
            <div v-if="mobileMenu" class="mobile-menu" :class="{ 'mobile-menu--active' : mobileMenu }">
              <div @click="openAbout">About Us</div>
              <nuxt-link to='PhysioTherapy' tag='div'>Services</nuxt-link>
              <nuxt-link to='career' tag='div'>Careers</nuxt-link>
            </div>
          </transition>
        </div>
      </div>
    </div>

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
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMobile: false,
      mobileMenu: false,
      aboutModal: false,
    };
  },
  mounted() {
    this.checkMobile();
  },
  methods: {
    checkMobile() {
      window.matchMedia('screen and ( max-width: 768px )').matches
        ? (this.isMobile = true)
        : (this.isMobile = false);
    },
    toggleMenu() {
      this.mobileMenu = ! this.mobileMenu;
    },
    openAbout() {
      this.aboutModal = true;
    },
  },
};
</script>

<style lang="scss" scoped>
.copy-right {
  z-index: 1;
  color: white;
  position: relative;
  text-align: center;
  padding: 1rem 0;
}

.mobile-menu {
  position: absolute;
  top: 0;
  width: 100%;
  background: #f7fefd;
  left: 0;
  right: 0;
  flex-direction: column;
  align-items: center;
  transition: all 0.3s ease-in-out;
  z-index: 5;
  display: flex;
  transform: translateY(-100%);
  box-shadow: 0 34px 42px -65px black;

  div {
    padding: 1.5rem;
    color: var(--color-orange);
    font-size: 1.6rem;
    width: 100%;
    text-align: center;
    position: relative;

    &:not(:last-child)::after {
    content: '';
    position: absolute;
    background: #a8d0cd;
    width: 6rem;
    height: 2px;
    bottom: 0;
    margin: auto;
    left: 0;
    right: 0;
    }
  }
}

.mobile-nav {
  background-color: var(--color-white);
  display: flex;
  justify-content: space-around;
  align-items: center;
  position: relative;
  position: fixed;
  bottom: 0;
  width: 100%;
  z-index: 10;
  box-shadow: 0 14px 32px 15px rgba(109, 109, 109, 0.19);

  @media (min-width: 1024px) {
    display: none;
  }

  &__item {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 5rem;
    padding: 1rem;
    cursor: pointer;

    img {
      width: 5rem;
      height: 5rem;
    }

    span {
      margin-top: 0.5rem;
    }
  }
}

.footer__shape{
  background: linear-gradient(135.34deg, #e87492 0%, #cd3e63 100%);
  position: absolute;
  bottom: -20%;
  left: 0;
  right: 0;
  width: 100%;
  height: 65rem;
  border-radius: 30px 0 0 0;
  transform: skewY(-15deg);

  @media (min-width:1024px) {
    height: 75rem;
    bottom: -25%;
    max-height: 100rem;
  }
}

.footer {
  padding-top: 9rem;
  margin: 0 auto;
  max-width: 110rem;
  width: 100%;

  &__info-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;

    @media (min-width:1024px) {
      flex-direction: row;
      align-items: inherit;
      justify-content: center;
      box-shadow: 0 -11px 33px -5px rgba(0, 0, 0, 0.09);
      margin: 3rem;
    }
  }

  &-icon {
    font-size: 3rem;

    &--orange {
      color: var(--color-orange);
      margin-right: 3rem;
    }

    &--teal {
      color: var(--color-teal);
    }
  }
}

.footer-item-container {
  width: 70%;

  @media (min-width:1024px) {
    flex-basis: 30%;
    height: 35rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background: white;
    padding: 2rem;
  }
}

.footer-iframe {
  flex-basis: 70%;

  iframe {
    width: 100%;
    height: 100%;
  }

  @media (max-width:1024px) {
    display: none;
  }
}

.footer-item {
  display: flex;
  align-items: center;

  &:not(:last-child) {
    margin-bottom: 2rem;
  }

  &__info {
    flex: 1;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
  }

  &__text {
    color: var(--color-light-pink);
    margin: 0;

    @media (min-width: 1024px) {
      color: black;
    }
  }

  &__link {
    color: var(--color-white);

    @media (min-width: 1024px) {
      color: var(--color-orange);
    }
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
