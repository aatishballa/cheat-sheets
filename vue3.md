# Vue 3 - Cheat Sheet

1.  [ref](#ref)
1.  [reactive](#reactive)
1.  [props](#props)
1.  [event handlers](#event-handlers)
1.  custom events
1.  v-model
1.  computed
1.  watchers
1.  slots
1.  lifecycle hooks
1.  composables
1.  provide/inject
1.  teleport
1.  suspense
1.  custom directives
1.  pinia

### ref

> **Note:** `ref()` returns a ref object with a `.value` property

```javascript
<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)
const object = ref({ id: 1, name: 'John', tags: ['client','male'] })

function changeName() {
  object.value.name = 'Jane'
}

function addTag() {
  object.value.tags.push('new tag')
}

function increment() {
  count.value++
}
</script>
```

### reactive

```javascript
<script setup lang="ts">
import { reactive } from 'vue'

const state = reactive({
  count: 0
})

function increment() {
  state.count++
}

</script>
```

### props

```javascript
<script setup lang="ts">
  interface message {
    id: number,
    msg: string,
    size: number
  }
  const props = withDefaults(defineProps<{
   userId: number,
   message: message
  }>(), {
    msg: {
      id: 1,
      msg: 'Hello World',
      size: 12
    }
  })
</script>

```

### event handlers
> **Note:** @change, @focus, @change etc

```javascript
<template>
  <button @click="increment">Increment</button>
</template>

<script setup lang="ts">
  function increment(e: Event) {
    console.log((e.target as HTMLInputElement).value)
  }
</script>

```

### custom events

```javascript
<template>

</template>

<script setup lang="ts">

</script>
```

### lifecycle hooks

```javascript 
<script setup lang="ts">
  import { onMounted, onUpdated, onUnmounted } from 'vue'

  onMounted(() => {
    console.log('mounted')
  })

  onUpdated(() => {
    console.log('updated')
  })

  onUnmounted(() => {
    console.log('unmounted')
  })
</script>

```  