<template>
  <div class="q-pa-sm">
    <div class="row items-start full-width justify-center">
      <div class="col-auto">
        <q-input
          class="text-h6"
          input-class="text-center text-primary"
          dense
          borderless
          v-model="counterName"/>
      </div>
    </div>
    <div class="row items-center justify-center">
      <div class="col-auto">
        <q-btn
          flat
          color="grey-8"
          icon="remove"
          round
          @click="counter -= 1"
          :disabled="counter<1"
          class="q-mx-sm"
          size="lg"
        />
      </div>
      <div class="col-auto q-px-xs">
        <div class="row text-h4 text-white justify-center">{{ counter }}</div>
      </div>
      <div class="col-auto">
        <q-btn
          flat
          color="grey-8"
          icon="add"
          round
          @click="counter += 1"
          size="lg"
          class="q-mx-sm"
        />
      </div>
    </div>
    <div class="row justify-center">
      <div class="col-auto">
        <q-btn
          flat
          color="grey-8"
          icon="refresh"
          round
          @click="counter = 0"
          size="sm"
        />
        <q-btn
          size="sm"
          flat
          round
          color="grey-8"
          icon="delete"
          @click="$emit('remove-counter')"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: ['instances'],
  data() {
    return {
      counter: 0,
      counterName: 'Name',
    };
  },
};
</script>

<style scoped>

</style>
