<template>
  <div class="secondary-page">
    <div class="hero-container">
      <div class="header__buttons">
        <header-logo></header-logo>
        <nav-buttons class="nav-buttons"></nav-buttons>
      </div>
    </div>
    <div class="wrapper df jcc">
      <div class="secondary-page__content">
        <div class="top-padding">
          <div class="secondary-page__title-container">
            <img class="secondary-page__logo" src="~/assets/images/secondary-page-logo.png" alt />
            <h2>Join Us For An Exciting Career</h2>
          </div>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis lobortis dapibus massa eu consequat. Suspendisse vitae metus lorem. Nunc euismod massa ac facilisis semper. Vivamus aliquam dolor eget lacus blandit porta. Integer sagittis lorem id tempor eleifend. Phasellus eu ultrices dui. Ut convallis rutrum aliquet. Vivamus vitae nunc turpis. Morbi in sapien tortor. Maecenas iaculis tortor vel tortor scelerisque, ut ornare nulla sagittis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vivamus cursus fringilla odio eget maximus. Donec scelerisque urna quis nulla lobortis malesuada. Sed consequat turpis in arcu rutrum, quis malesuada ligula placerat. Pellentesque cursus rutrum lacus ac ullamcorper. Aliquam dolor magna, commodo in elementum id, malesuada sed lacus.</p>
        </div>
        <div class="career-card">
          <div class="career-card__title">
            <h4>Registered Massage Therapist</h4>
            <div class="career-card__button-container">
              <div class="button button--hollow">Learn More</div>
              <div class="button button--green">Apply Now</div>
            </div>
          </div>
          <div class="career-card__requirement">
            <i class="fas fa-book"></i>
            <b>Level of Education: Bachelors Degree</b>
          </div>
          <div class="career-card__requirement">
            <i class="far fa-calendar-check"></i>
            <b>Years of Experience: 5+ </b>
          </div>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis lobortis dapibus massa eu consequat. Suspendisse vitae metus lorem. Nunc euismod massa ac facilisis semper. Vivamus aliquam dolor eget lacus blandit porta. Integer sagittis lorem id tempor eleifend. Phasellus eu ultrices dui. Ut convallis rutrum aliquet. Vivamus vitae nunc turpis. Morbi in sapien tortor. Maecenas iaculis tortor vel tortor scelerisque, ut ornare nulla sagittis. Orci varius natoque penatibus et</p>
        </div>
        <div class="career-card">
          <div class="career-card__title">
            <h4>Receptionist</h4>
            <div class="career-card__button-container">
              <div class="button button--hollow">Learn More</div>
              <div class="button button--green">Apply Now</div>
            </div>
          </div>
          <div class="career-card__requirement">
            <i class="fas fa-book"></i>
            <b>Level of Education: Bachelors Degree</b>
          </div>
          <div class="career-card__requirement">
            <i class="far fa-calendar-check"></i>
            <b>Years of Experience: 5+ </b>
          </div>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis lobortis dapibus massa eu consequat. Suspendisse vitae metus lorem. Nunc euismod massa ac facilisis semper. Vivamus aliquam dolor eget lacus blandit porta. Integer sagittis lorem id tempor eleifend. Phasellus eu ultrices dui. Ut convallis rutrum aliquet. Vivamus vitae nunc turpis. Morbi in sapien tortor. Maecenas iaculis tortor vel tortor scelerisque, ut ornare nulla sagittis. Orci varius natoque penatibus et</p>
        </div>
      </div>
    </div>
    <div class="footer-wrapper">
      <vue-footer></vue-footer>
    </div>
  </div>
</template>

<script>
import NavButtons from '~/components/NavButtons.vue';
import VueFooter from '~/components/Footer.vue';
import HeaderLogo from '~/components/HeaderLogo.vue';

export default {
  components: {
    NavButtons,
    HeaderLogo,
    VueFooter,
  },
};
</script>

<style lang="scss" scoped>

.secodary-page-footer-wrapper {
  position: relative;
}

.secondary-page__content {
  padding: 2rem 0;
}

.top-padding {
  padding: 0 2rem;

  @media (min-width: 1024px) {
    padding: 0 6rem;
  }
}

.hero-container {
    background-image: url("../assets/images/physio-hero-banner.jpg");
}

.career-card {
  box-shadow: 0 20px 35px 12px rgba(138,141,141,0.09);
  border-radius: 5px;
  padding: 2rem;
  margin-bottom: 2rem;

  &__title {
    display: flex;
    flex-direction: column;

    @media (min-width: 1024px) {
      align-items: center;
      justify-content: space-between;
      flex-direction: row;
    }

    h4 {
      color: var(--color-teal);
      margin: 0;
    }
  }

  &__button-container {
    display: flex;
    margin: 2rem 0;

    @media (min-width: 1024px) {
      margin: 0;
    }
  }

  &__requirement {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;

    i {
      color: var(--color-orange);
      margin-right: 1rem;
      font-size: 2rem;
    }

    b {
      font-size: 16px;
    }
  }
}

.button {
  height: 4rem;
  width: 12rem;
  border-radius: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease-in-out;
  cursor: pointer;
  font-size: 1.2rem;

  &:nth-child(1) {
    margin-right: 1rem;
  }

  &--hollow {
    color: #808080;
    border: 2px solid #808080;
    background: transparent;

    &:hover {
      background: #808080;
      color: white;
    }
  }

  &--green {
    background: linear-gradient(135.02deg, #5DC9C1 0%, #2FB1A7 100%);
    color: white;
  }
}
</style>
