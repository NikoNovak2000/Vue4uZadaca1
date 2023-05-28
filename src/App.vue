<template>
  <InputForm @dodajUser="dodajUser" />
  <UserList :users="users" @izbrisiUser="izbrisiUser" />
</template>

<script>
import InputForm from './components/InputForm.vue'
import UserList from './components/UserList.vue'
import { ref } from 'vue'

export default {
  components: {
    InputForm,
    UserList
  },
  setup() {
    const users = ref([])

    function dodajUser(user) {
      users.value.push({
        id: users.value.length + 1,
        ...user
      })
    }
    function izbrisiUser(userId) {
      users.value = users.value.filter((user) => user.id !== userId)
    }

    return {
      users,
      dodajUser,
      izbrisiUser
    }
  }
}
</script>
