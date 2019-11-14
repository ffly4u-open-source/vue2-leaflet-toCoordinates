<template>
  <div style="display: none;">
    <slot v-if="ready"></slot>
  </div>
</template>

<script>
import LeafletToCoordinates from 'leaflet-tocoordinates';

const props = {
  options: {
    type: Object,
    default() { return {}; },
  },
  visible: {
    type: Boolean,
    custom: true,
    default: true,
  },
};

export default {
  name: 'VToCoordinates',
  props,
  data: () => ({
    ready: false,
  }),
  beforeDestroy() {
    // Important for hot-reload to destroy previous instance of control
    this.$parent.mapObject.removeControl(this._control);
    if (this.markerCluster) {
      this.$parent.removeLayer(this.markerCluster);
    }
  },
  mounted() {
    // Add control only if parent is mounted
    if (this.$parent._isMounted) {
      this._control = new LeafletToCoordinates(this.options);
      this.$parent.mapObject.addControl(this._control);
    }
  },
};
</script>
