<template>
  <b-collapse :id="id + '-list-group'"
              :visible="visible">
    <b-list-group flush>
      <b-list-group-item v-for="rule in rules"
                          :key="rule.id">
        {{ rule.description }}
        <div v-if="rule.availableSince"
              class="rule-available-since">
          Karabiner-Elements {{ rule.availableSince }} or later
        </div>
      </b-list-group-item>
      <b-list-group-item v-if="extraDescription"
                          v-html="extraDescription">
      </b-list-group-item>
    </b-list-group>
  </b-collapse>
</template>

<script>
export default {
  props: [
    'id',
    'rules',
    'extraDescription',
    'visible'
  ]
}
</script>
