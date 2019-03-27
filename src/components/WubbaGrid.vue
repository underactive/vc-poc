<template>
  <div>
    <div class="w3-row-padding">
      <button @click="getCharacterList()">Update Character List</button>
    </div><br />
    <!-- First Photo Grid-->
    <div class="w3-row-padding" v-for="(i,index) in rowCount" :key="index">
      <div class="w3-third w3-container w3-margin-bottom" v-for="(character,index) in characters.slice((i - 1) * 3, i * 3)" :key="index">
        <img :src="character.image" :alt="character.name" style="width:100%" class="w3-hover-opacity">
        <div class="w3-container w3-white">
          <p><b>{{ character.name }}</b></p>
          <p>Origin: {{ character.origin.name }}</p>
          <p>Species: {{ character.species }}</p>
          <p>Status: {{ character.status }}</p>
          <p># Episodes: {{ character.episode.length }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'WubbaGrid',

  data () {
    return {
      characters: []
    }
  },

  created () {
    this.getCharacterList()
  },

  methods: {
    async getCharacterList () {
      const numRnd = Math.floor(Math.random() * 14) + 3
      const rndCharsN = this.randomize(numRnd, 100).join(',')
      await axios.get(`https://rickandmortyapi.com/api/character/${rndCharsN}`).then((response) => {
        this.characters = response.data
      })
    },

    randomize (length, max) {
      return Array.apply(null, Array(length)).map(() => Math.round(Math.random() * max))
    }
  },

  computed: {
    rowCount () {
      return Math.ceil(this.characters.length / 3)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
