<template>
  <div>
    <div v-if="users.length === 0">Nema user-a</div>
    <div v-for="user in users" :key="user.id" class="user-card">
      <img :src="user.slika" />
      <p>{{ user.ime }}</p>
      <p>{{ user.opis }}</p>
      <button @click="izbrisiUser(user.id)">Izbriši</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    users: {
      type: Array,
      default: () => []
    }
  },
  emits: ['izbrisiUser'],
  methods: {
    removeUser(userId) {
      this.$emit('izbrisiUser', userId)
    }
  }
}
</script>
