<template>
  <q-page class="flex flex-center bg-dark">
    <div class="row full-width">
      <div class="col">
        <Counter
          v-for="(item, index) in instances"
          :key="index"
          @remove-counter="removeCounter(index)"
        />
      </div>
    </div>
    <div class="row justify-center full-width">
      <q-btn class="q-ma-md" label="add counter" color="primary" @click="addCounter()"/>
    </div>
  </q-page>
</template>

<script>
import Counter from 'components/Counter';

export default {
  name: 'PageIndex',
  components: { Counter },

  data() {
    return {
      instances: [{}],
    };
  },

  methods: {
    addCounter() {
      this.instances.push({ });
    },
    removeCounter(index) {
      this.instances.splice(index, 1);
    },
  },
};
</script>
