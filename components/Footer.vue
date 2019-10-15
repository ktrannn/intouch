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
        <div class="mobile-nav__item">
          <div class="footer-icon footer-icon--teal">
            <i class="fas fa-bars"></i>
          </div>
          <span>Menu</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMobile: false,
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
      console.log('clicked');
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

.mobile-nav {
  background-color: var(--color-white);
  display: flex;
  justify-content: space-around;
  align-items: center;
  position: relative;

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
</style>
