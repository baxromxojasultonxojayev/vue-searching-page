<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButton">Stored Resource</base-button>
    <base-button @click="setSelectedTab('add-resource')" :mode="addResButton">Add Resource</base-button>

    <keep-alive>
      <component :is="selectedTab"></component>
    </keep-alive>
  </base-card>
</template>


<script>
import StoredResources from './StoredResources.vue'
import AddResource from './AddResource.vue'
export default {
  components: {
    StoredResources,
    AddResource
  },
  data() {
    return{
      selectedTab: 'stored-resources',
      sortedResource: [
        {
          id: 'official-site',
          title: `Najot ta'lim`,
          description: `Ushbu oquv markazda turli xil yo'nalishlar mavjud`,
          link: 'https://najottalim.uz/'
        },
        {
          id: 'official-site',
          title: 'Google',
          description: 'Welcome to google',
          link: 'http://google.com'
        }
      ]
    }
  },
  provide() {
    return {
      resources: this.sortedResource, 
      addResource: this.addResource,
      deleteResource: this.removeResource
    }
  },
  computed: {
    storedResButton(){
      return this.selectedTab == 'sorted-resources' ? null : 'flat'
    },
    addResButton(){
      return this.selectedTab == 'add-resource' ? null : 'flat'
    }
  },
  methods: {
    setSelectedTab(tab){
      this.selectedTab = tab
    },
    addResource(title, description, url){
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: url
      }
      this.sortedResource.unshift(newResource)
      this.selectedTab = 'stored-resources'
    },
    removeResource(resId){
      const indexId = this.sortedResource.findIndex(res => res.id === resId)
      this.sortedResource.splice(indexId, 1)
    }
  }
}
</script>

<style  scoped>
button{
  margin: 10px
}
</style>