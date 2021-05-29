<template>
  <base-diolog v-if="inpudIsInvalid"  title="Invalid Input" @close="confirmError">
    <template #default>
      <p>Please full in all gaps</p>   
    </template>

    <template #actions>
      <base-button @click="confirmError">OK</base-button>
    </template>
  </base-diolog>

  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input type="text" id="title" name="title" ref="titleInput">
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="5" ref="descriptionInput"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input type="url" id="link" name="link" ref="linkInput">
      </div>
      <div>
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
// import BaseButton from '../UI/BaseButton.vue'
export default {
  // components: { BaseButton },
  
  inject: ['addResource'],
  data(){
    return{
      inpudIsInvalid: false
    }
  },
  methods: {
    submitData(){
      const enteredTitle = this.$refs.titleInput.value
      const enteredDescription = this.$refs.descriptionInput.value
      const enteredLink = this.$refs.linkInput.value

      if(enteredTitle.trim() === '' || enteredDescription.trim() === '' || enteredLink.trim() === ''){
        this.inpudIsInvalid = true
        return
      }

      this.addResource(enteredTitle, enteredDescription, enteredLink)
    },
    confirmError(){
      this.inpudIsInvalid = false
    }
  }
}
</script>


<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
  resize: none;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
