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
        <div class="secondary-page__title-container">
          <img class="secondary-page__logo" src="~/assets/images/secondary-page-logo.png" alt />
          <h2>Experienced Physiotherapy</h2>
        </div>
        <div>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis lobortis dapibus massa eu consequat. Suspendisse vitae metus lorem. Nunc euismod massa ac facilisis semper. Vivamus aliquam dolor eget lacus blandit porta. Integer sagittis lorem id tempor eleifend. Phasellus eu ultrices dui. Ut convallis rutrum aliquet. Vivamus vitae nunc turpis. Morbi in sapien tortor. Maecenas iaculis tortor vel tortor scelerisque, ut ornare nulla sagittis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vivamus cursus fringilla odio eget maximus. Donec scelerisque urna quis nulla lobortis malesuada. Sed consequat turpis in arcu rutrum, quis malesuada ligula placerat. Pellentesque cursus rutrum lacus ac ullamcorper. Aliquam dolor magna, commodo in elementum id, malesuada sed lacus.
          </p>
          <p>
            Mauris magna quam, rhoncus id nulla at, vehicula elementum sem. Ut consequat, ex vitae elementum suscipit, sem urna facilisis dui, nec lobortis est mi et nibh. Fusce vestibulum at sem id sagittis. Aliquam sit amet est non neque ornare faucibus non in mauris. Maecenas facilisis, neque non faucibus malesuada, mauris neque pretium lorem, sit amet venenatis turpis metus vel augue. Phasellus eu imperdiet erat, et congue urna. Nullam interdum felis facilisis nisl aliquam ullamcorper. Pellentesque scelerisque, tortor at convallis tempor, ante nisl lacinia massa, vitae placerat leo enim eu erat.
          </p>
          <div class="secondary-page__image">
            <img src="~/assets/images/physio-image.png" alt />
          </div>
          <h3>What About My Benefits?</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis lobortis dapibus massa eu consequat. Suspendisse vitae metus lorem. Nunc euismod massa ac facilisis semper. Vivamus aliquam dolor eget lacus blandit porta. Integer sagittis lorem id tempor eleifend. Phasellus eu ultrices dui. Ut convallis rutrum aliquet. Vivamus vitae nunc turpis. Morbi in sapien tortor. Maecenas iaculis tortor vel tortor scelerisque, ut ornare nulla sagittis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vivamus cursus fringilla odio eget maximus. Donec scelerisque urna quis nulla lobortis malesuada. Sed consequat turpis in arcu rutrum, quis malesuada ligula placerat. Pellentesque cursus rutrum lacus ac ullamcorper. Aliquam dolor magna, commodo in elementum id, malesuada sed lacus.
            Mauris magna quam, rhoncus id nulla at, vehicula elementum sem. Ut consequat, ex vitae elementum suscipit, sem urna facilisis dui, nec lobortis est mi et nibh. Fusce vestibulum at sem id sagittis. Aliquam sit amet est non neque ornare faucibus non in mauris. Maecenas facilisis, neque non faucibus malesuada, mauris neque pretium lorem, sit amet venenatis turpis metus vel augue. Phasellus eu imperdiet erat, et congue urna. Nullam interdum felis facilisis nisl aliquam ullamcorper. Pellentesque scelerisque, tortor at convallis tempor, ante nisl lacinia massa, vitae placerat leo enim eu erat.
          </p>
          <p>
            Mauris magna quam, rhoncus id nulla at, vehicula elementum sem. Ut consequat, ex vitae elementum suscipit, sem urna facilisis dui, nec lobortis est mi et nibh. Fusce vestibulum at sem id sagittis. Aliquam sit amet est non neque ornare faucibus non in mauris. Maecenas facilisis, neque non faucibus malesuada, mauris neque pretium lorem, sit amet venenatis turpis metus vel augue. Phasellus eu imperdiet erat, et congue urna. Nullam interdum felis facilisis nisl aliquam ullamcorper. Pellentesque scelerisque, tortor at convallis tempor, ante nisl lacinia massa, vitae placerat leo enim eu erat.
          </p>
        </div>
      </div>
    </div>
    <div class="footer-wrapper">
      <vue-footer></vue-footer>
    </div>
  </div>
</template>

<script>
import VueFooter from '~/components/Footer.vue';
import NavButtons from '~/components/NavButtons.vue';
import HeaderLogo from '~/components/HeaderLogo.vue';

export default {
  components: {
    NavButtons,
    VueFooter,
    HeaderLogo,
  },
};
</script>

<style lang="scss" scoped>
.hero-container {
    background-image: url("../assets/images/physio-hero-banner.jpg");
}
</style>
