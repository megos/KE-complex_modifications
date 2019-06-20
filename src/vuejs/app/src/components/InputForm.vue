<template>
  <b-form @submit="submit">
    <b-input-group>
      <b-form-input v-model="searchQuery"
                    :disabled="disabled"
                    :placeholder="(!disabled ? 'Search keywords...' : 'Fetching data...')">
      </b-form-input>
      <b-input-group-append>
        <b-btn type="submit"
                variant="primary">Search</b-btn>
      </b-input-group-append>
    </b-input-group>
  </b-form>
</template>

<script>
export default {
  props: [
    'disabled'
  ],
  data() {
    return {
      searchQuery: ''
    }
  },
  methods: {
    submit(e) {
      e.preventDefault()
      this.$emit('submit', this.searchQuery)
    }
  }
}
</script>