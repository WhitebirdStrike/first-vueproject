onBeforeMount(() => { console.log("onBeforeMount"); }); onMounted(() => {
console.log("onMounted"); }); onBeforeUnmount(() => {
console.log("onBeforeUnmount"); }); onUnmounted(() => {
console.log("onUnmounted"); }); onActivated(() => { console.log("onUnmounted");
}); onDeactivated(() => { console.log("onDeactivated"); });
<!--
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  computed: {
    myComputedProperty() {
      return 'my result'
    }
  },
  watch: {
    count(newCount, oldCount) {
      if (newCount == 20) alert('20 pingas')
    }
  },
  mounted() {
    console.log('mounted')
  },
  unmounted() {
    console.log('unmounted')
  }
}

</script>
-->
<!--
<script>
import { ref } from "vue";

export default {
  setup() {
    const counter = ref(0);

    const increaseCounter = () => {
      counter.value++;
    };

    const decreaseCounter = () => {
      counter.value--;
    };

    return {
      counter,
      decreaseCounter,
      increaseCounter,
    };
  },
};
</script>
-->

<!--
<script>
export default {
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    increaseCounter() {
      this.counter++;
    },
    decreaseCounter() {
      this.counter--;
    },
  },
};
</script>
-->
onBeforeMount, onMounted, onBeforeUnmount, onUnmounted, onActivated,
onDeactivated, onBeforeUpdate, onUpdated onBeforeUpdate(() => {
console.log("onBeforeUpdate"); }); onUpdated(() => { console.log("onUpdated");
}); //const counter = ref(0); //const counterTitle = ref("My Counter");

<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <h1>This is a modal</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellendus
      accusamus molestias quia commodi perferendis voluptatem voluptatibus,
      aliquid id culpa modi, quae amet impedit magnam accusantium ut iure magni!
      Dolorum, officia.
    </p>
    <button @click="showModal = true">Hide modal</button>
    <Modal v-if="showModal"></Modal>
  </div>
</template>

<script setup>
/*
imports
*/

import { ref } from "vue";

/*
modals
*/

const showModal = ref(false);
</script>

<!--
<script>
import Modal from "@/components/Modal.vue";

export default {
  components: {
    Modal,
  },
};
</script>
-->

<template>
  <teleport to=".modals-container">
    <div class="modal">
      <h1>This is a modal</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellendus
        accusamus molestias quia commodi perferendis voluptatem voluptatibus,
        aliquid id culpa modi, quae amet impedit magnam accusantium ut iure
        magni! Dolorum, officia.
      </p>
      <button>Hide modal</button>
    </div>
  </teleport>
</template>

<style>
.modal {
  background: beige;
  padding: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}
</style>
