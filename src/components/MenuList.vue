<template>
  <div class="text-center mt-5">
    <v-menu top
      :offset-x="offset">
      <template v-slot:activator="{ on, attrs }">
        <v-btn color="primary" dark v-bind="attrs" v-on="on">
          Show List
        </v-btn>
      </template>
      <v-list v-scroll.self="onScroll">
        <v-list-item v-for="(item, index) in renderedList" :key="index">
          <v-list-item-title>{{ item }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "MenuList",
  data() {
    return {
      renderedList: [],
      items_length: this.items.length,
      chunk: 20,
      rendered_length: 0,
      offset_pixels: 100,
    };
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  beforeMount() {
    this.rendered_length += this.chunk;
    this.renderedList = this.items.slice(0, this.rendered_length + 1);
  },
  methods: {
    addChunk: function() {
      this.rendered_length += this.chunk;
      this.renderedList = this.items.slice(0, this.rendered_length + 1);
    },
    onScroll: function(e) {
      if (e.target.scrollTop + e.target.offsetHeight > e.target.scrollHeight - this.offset_pixels ) {
        if (this.rendered_length + 1 < this.items_length) this.addChunk();
      }
    },
  },
};
</script>

<style>
.v-list {
  height: 300px;
  overflow-y: auto;
}
</style>
