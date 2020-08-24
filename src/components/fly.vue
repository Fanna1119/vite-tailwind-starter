<template>
  <button @click="open = true">open telporpted modal</button>

  <br />

  <teleport to="#portal">
    <div v-if="open" :style="portal[to]">
      <div class="modal bg-blue-500">
        <slot></slot>

        <div class="absolute bottom-0">
          <button @click="open = false">close</button>
        </div>
      </div>
    </div>
  </teleport>
</template>


<script>
export default {
  props: ["to"],
  name: "fly",
  props: {
      to: {
          default: "full",
          validator: () => ["full", "left"]
      }
  },
  data() {
    return {
      open: false,
      portal: {
        left: {
          position: "fixed",
          top: 0,
          zIndex: 10,
          backgroundColor: "#f5f5f5",
          bottom: 0,
          right: "75vw",
          left: 0,
        },

        full: {
          position: "fixed",
          top: 0,
          zIndex: 10,
          // backgroundColor: "blue",
          bottom: 0,
          right: 0,
          left: 0,
        },
      },
    };
  },
};
</script>

<style>
</style>