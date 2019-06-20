<template>
  <icon :name="`caret-square-${collapsed ? 'right' : 'down'}`"></icon>
</template>

<script>
export default {
  props: [
    'collapsed'
  ]
}
</script>
