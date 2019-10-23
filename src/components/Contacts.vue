<template>
  <div class="contacts">
    <div class="container cont">
      <div class="row">
        <div class="col-lg-12 col-md-12 col-sm-12" style="margin-bottom: 1.5em;">
          <h1>Contacts</h1>
        </div>
        <div class="col-lg-6 col-md-6 col-sm-12">
          <h2 style="margin-bottom: 1em;">
            <span>GMS</span> Headquarters
          </h2>
          <div class="row">
            <div class="col-lg-6 col-md-6 col-sm-12">
              <p class="adress">Global Message Services Ukraine LLC</p>
              <p class="adress">Bundesstrasse 5 | 3rd Floor</p>
              <p class="adress">6300 Zug</p>
              <p class="adress">Switzerland</p>
              <br />
              <a class="phone" href="tel:+41415446200">
                <h3>+41 41 544 62 00</h3>
              </a>
            </div>
            <div class="col-lg-6 col-md-6 col-sm-12">
              <p class="adress">Email</p>
              <a class="link" href="mailto:info@gms-worldwide.com">info@gms-worldwide.com</a>
              <p class="adress">Send message</p>
              <a class="link" href="#">Viber us</a>
              <p class="adress">Send form</p>
              <a class="link" href="#">Contact us</a>
            </div>
          </div>
        </div>
        <div class="col-lg-6 col-md-6 col-sm-12">
          <h2 style="margin-bottom: 1em;">
            Technical support
            <span>24/7</span>
          </h2>
          <div class="row">
            <div class="col-lg-12 col-md-12 col-sm-12">
              <p
                class="technical-support"
              >GMS understands that it can be hard to follow all new technologies. We regularly provide for all our clients educational trainings to make your operator`s business earn more and better though our best practices.</p>
              <br />
              <a class="phone" href="tel:+41415446206">
                <h3>+41 41 544 62 06</h3>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$color-green: #3db565;
@font-face {
  font-family: SuisseIntl;
  src: url("./../assets/fonts/SuisseIntl-Light.woff");
  src: url("./../assets/fonts/SuisseIntl-Light.woff2");
}
@font-face {
  font-family: SuisseIntB;
  src: url("./../assets/fonts/SuisseIntl-SemiBold.woff");
  src: url("./../assets/fonts/SuisseIntl-SemiBold.woff2");
}
@font-face {
  font-family: SuisseIntR;
  src: url("./../assets/fonts/SuisseIntl.woff");
  src: url("./../assets/fonts/SuisseIntl.woff2");
}
h1,
h2,
h2,
h3,
h5,
h6,
h6,
p {
  font-family: SuisseIntl;
}
.contacts {
  width: 100%;
  height: 477px;
}
.cont {
  margin-top: 60px;
}
.adress {
  margin-top: 0.5em;
  margin-bottom: 0.5em;
}
.technical-support {
  margin-top: 0.5em;
  margin-bottom: 0.5em;
}
.link {
  font-family: SuisseIntB;
  text-transform: uppercase;
  color: $color-green;
}
.phone {
  color: $color-green;
}
span {
  color: $color-green;
}
@media (max-width: 767px) {
  .contacts {
    height: auto;
  }
}
</style>
