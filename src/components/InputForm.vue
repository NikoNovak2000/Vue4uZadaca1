<template>
  <div>
    <input v-model="ime" type="text" placeholder="opis" />
    <input v-model="opis" type="text" placeholder="ime" />
    <input v-model="slika" type="text" placeholder="slika" />
    <button @click="dodajUser">Dodaj User-a</button>
  </div>
</template>

<script>
import { defineEmits } from 'vue'
export default {
  emits: ['dodajUser'],
  data() {
    return {
      ime: '',
      opis: '',
      slika: ''
    }
  },
  methods: {
    dodajUser() {
      if (!this.ime || !this.opis || !this.slika) {
        alert('Nisi sve popunio')
        return
      }
      this.$emit('dodajUser', {
        ime: this.ime,
        opis: this.opis,
        slika: this.slika
      })

      ;(this.ime = ''), (this.opis = ''), (this.slika = '')
    }
  }
}
</script>
