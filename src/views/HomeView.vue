<template>
  <div class="home">
    <div>Param "tab" is {{ tab }}</div>
    <button @click="tab = 'foo'">Set param to 'foo'</button>
  </div>
</template>

<script>
import { toRefs } from '@vue/composition-api'
import { useUrlSearchParams } from '@vueuse/core';

export default {
  name: 'HomeView',
  setup() {
    const params = useUrlSearchParams('history', {
      initialValue: { tab: 'baz' }
    });

    return toRefs(params)
  }
}
</script>
