# vue2-leaflet-toCoordinates
This is a [toCoordinates plugin](https://github.com/ffly4u-open-source/leaflet-toCoordinates) extension for [vue2-leaflet package](https://github.com/KoRiGaN/Vue2Leaflet)

## Install

with npm:
```bash
npm install --save @ffly4u/leaflet-tocoordinates @ffly4u/vue2-leaflet-tocoordinates
```

or yarn:
```bash
yarn add @ffly4u/leaflet-tocoordinates @ffly4u/vue2-leaflet-tocoordinates
```

## Usage

Look [toCoordinates plugin Options](https://github.com/ffly4u-open-source/leaflet-toCoordinates#options) for options

``` html
<v-map :zoom=3 :center="location">
  <v-tilelayer url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"></v-tilelayer>
  <!-- IMPORTANT PART HERE -->
  <v-to-coordinates :options="toCoordinatesOptions" ></v-to-coordinates>
  <!-- /IMPORTANT PART HERE -->
</v-map>

<script>
import Vue from 'vue';
import Vue2Leaflet from 'vue2-leaflet';
import VToCoordinates from 'vue2-leaflet-toCoordinates';

Vue.component('v-map', Vue2Leaflet.Map);
Vue.component('v-tilelayer', Vue2Leaflet.TileLayer);

export default {
  components: { VToCoordinates },
  data() {
    return {
      toCoordinatesOptions: {
        // options
      },
    };
  },
};
</script>
```

# License

[MIT](https://github.com/ffly4u-open-source/vue2-leaflet-toCoordinates/blob/master/LICENSE)
