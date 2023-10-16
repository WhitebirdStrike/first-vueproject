<template>
  <div class="modals">
    <h1>Modals</h1>
    <div>
      <label
        >Show dark modals???
        <input v-model="showDarkModals" type="checkbox" />
      </label>
    </div>
    <button @click="showModal = true">Show modal</button>
    <component
      v-model="showModal"
      :is="showDarkModals ? ModalDark : Modal"
      title="My modal title (via prop)"
    >
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellendus
        accusamus molestias quia commodi perferendis voluptatem voluptatibus,
        aliquid id culpa modi, quae amet impedit magnam accusantium ut iure
        magni! Dolorum, officia.
      </p>
    </component>
  </div>
</template>

<script setup>
/*
imports
*/

import { ref } from "vue";
import Modal from "@/components/global/Modal.vue";
import ModalDark from "@/components/global/ModalDark.vue";

/*
modals
*/

const showDarkModals = ref(false);
const showModal = ref(false);
</script>

<!-- <script>
import Modal from "@/components/global/Modal.vue";

export default {
  components: {
    Modal,
  },
};
</script>
-->
