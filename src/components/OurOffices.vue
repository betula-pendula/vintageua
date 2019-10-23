<template>
  <div class="our-offices">
    <div class="container">
      <div class="row">
        <div class="col-lg-6" style="margin-top: 100px;">
          <h2 style="margin-bottom: 1em;">Our Offices</h2>
          <!-- Nav pills -->
          <ul class="nav">
            <li class="nav-item" v-on:click="city='kiev', show=[true, false, false, false]">
              <a class="nav-link active" data-toggle="pill" href="#kyiv">KYIV</a>
            </li>
            <li class="nav-item" v-on:click="city='new york', show=[false, true, false, false]">
              <a class="nav-link" data-toggle="pill" href="#new">NEW YORK</a>
            </li>
            <li class="nav-item" v-on:click="city='guangzhou', show=[false, false, true, false]">
              <a class="nav-link" data-toggle="pill" href="#gua">GUANGZHOU</a>
            </li>
            <li class="nav-item" v-on:click="city='barcelona', show=[false, false, false, true]">
              <a class="nav-link" data-toggle="pill" href="#bar">BARCELONA</a>
            </li>
          </ul>
          <!-- Tab panes -->
          <div class="tab-content">
            <div class="tab-pane active tab-active" id="kyiv">
              <h3>Global Message Services Ukraine LLC</h3>
              <p>
                Kuiv, Stepan Bandera, 33
                <br />02066
                <br />Ukraine
              </p>
            </div>
            <div class="tab-pane fade tab-active" id="new">
              <h3>New York</h3>
              <p>
                New York, Stepan Bandera, 33
                <br />03456
                <br />USA
              </p>
            </div>
            <div class="tab-pane fade tab-active" id="gua">
              <h3>Guangzhou</h3>
              <p>
                Guangzhou, Stepan Bandera, 33
                <br />07076
                <br />Chine
              </p>
            </div>
            <div class="tab-pane fade tab-active" id="bar">
              <h3>Barcelona</h3>
              <p>
                Barcelona, Stepan Bandera, 33
                <br />06786
                <br />Spanish
              </p>
            </div>
          </div>
        </div>
        <div class="map" v-if="city == 'kiev'" v-bind:class="{ kyiv: show[0] }">
          <div class="pin"></div>
        </div>
        <div class="map" v-if="city == 'new york'" v-bind:class="{ newyork: show[1] }">
          <div class="pin"></div>
        </div>
        <div class="map" v-if="city == 'guangzhou'" v-bind:class="{ guangzhou: show[2] }">
          <div class="pin"></div>
        </div>
        <div class="map" v-if="city == 'barcelona'" v-bind:class="{ barcelona: show[3] }">
          <div class="dark"></div>
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d191555.2453954063!2d2.0086809815888564!3d41.39470509978519!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x12a49816718e30e5%3A0x44b0fb3d4f47660a!2z0JHQsNGA0YHQtdC70L7QvdCwLCDQmNGB0L_QsNC90LjRjw!5e0!3m2!1sru!2sua!4v1571827816712!5m2!1sru!2sua"
            width="100%"
            height="500"
            frameborder="0"
            style="border:0;"
            allowfullscreen
            class="filter"
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cities: [
        'KYIV', 'NEW YORK', 'GUANGZHOU', 'BARCELONA'
      ],
      city: 'kiev',
      show: [true, false, false, false]
    }
  },
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
$color-back: #262626;
.our-offices {
  position: relative;
  height: 500px;
  width: 100%;
  background: $color-back;
  color: white;
}
.content {
  position: absolute;
  margin-left: 100px;
}
.map {
  position: absolute;
  height: 500px;
  width: 50%;
  right: 0;
}
.city {
  font-size: 10pt;
  display: inline;
  margin-right: 25px;
  &:hover {
    color: $color-green;
    cursor: pointer;
  }
}
.nav-link {
  padding-left: 0;
  padding-right: 0;
  margin-right: 2em;
  color: white;
  font-size: 8pt;
  font-family: SuisseIntl;
  letter-spacing: 2px;
}
.active {
  color: $color-green;
}
.tab-active {
  margin-top: 2em;
  color: white;
  p {
    margin-top: 2em;
  }
}
.kyiv {
  background-image: url("./../assets/kyiv.png");
  background-size: cover;
}
.newyork {
  background-image: url("./../assets/ny.png");
  background-size: cover;
}
.guangzhou {
  background-image: url("./../assets/gua.png");
  background-size: cover;
}
.barcelona {
  background: white;
}
.pin {
  position: absolute;
  top: calc(50% - 15px);
  left: calc(50% - 15px);
  width: 30px;
  height: 30px;
  background: $color-green;
  -moz-border-radius: 30px;
  -webkit-border-radius: 30px;
  border-radius: 30px;
}
.filter {
  filter: grayscale(100);
}
@media (max-width: 767px) {
  .our-offices {
    height: auto;
  }
  .map {
    position: relative;
    height: 500px;
    width: 100%;
  }
}
</style>