<script setup>
defineProps({
  dialogState: {
    type: Boolean,
    required: true
  }
})
</script>

<template>
  <GDialog v-model="dialogState" max-width="500">
    <div class="wrapper">
      <div class="content">
        <div class="title">Bitcoin</div>

        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing
          elit. Porro, ratione!
        </p>
      </div>

      <div class="actions">
        <button
          class="btn btn--outline-gray"
          @click="dialogState = false"
        >
          Submit
        </button>
      </div>
    </div>
  </GDialog>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
