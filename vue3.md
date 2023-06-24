# Vue 3 - Cheat Sheet

1.  [ref](#ref)
1.  [reactive](#reactive)
1.  props
1.  event handlers
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
