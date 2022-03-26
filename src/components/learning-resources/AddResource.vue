<template>
  <base-dialog
    v-if="inputIsInvalid"
    title="Invalid Input"
    @close="confirmError"
  >
    <template #default>
      <p>Unfortunately, atleast 1 input value is invalid.</p>
      <p>
        Please check all the inputs and make sure you enter atleast few
        characters in each input field
      </p>
    </template>
    <template #actions>
      <base-button mode="success" @click="confirmError">Okay</base-button>
    </template>
  </base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div>
        <label for="title">Title</label>
        <input
          type="text"
          placeholder="Enter the title"
          v-model="enteredTitle"
        />
      </div>
      <div>
        <label for="description">Description</label>
        <textarea
          rows="3"
          placeholder="Enter the description"
          v-model="enteredDesc"
        ></textarea>
      </div>
      <div>
        <label for="link">Link</label>
        <input type="url" placeholder="Enter the link" v-model="enteredLink" />
      </div>
      <base-button type="submit" mode="success">Submit</base-button>
    </form>
  </base-card>
</template>

<script>
export default {
  data() {
    return {
      enteredTitle: '',
      enteredDesc: '',
      enteredLink: '',
      inputIsInvalid: false,
    };
  },
  inject: ['addResource'],
  methods: {
    //   here we are calling the addResource method, basically which gets injected from the Resources component
    submitData() {
      if (
        this.enteredTitle.trim() === '' ||
        this.enteredDesc.trim() === '' ||
        this.enteredLink.trim() === ''
      ) {
        this.inputIsInvalid = true;
        return;
      }

      this.addResource(this.enteredTitle, this.enteredDesc, this.enteredLink);
      this.enteredTitle = '';
      this.enteredDesc = '';
      this.enteredLink = '';
    },
    confirmError() {
      this.inputIsInvalid = false;
    },
  },
};
</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  font-family: inherit;
}
div label {
  margin: 6px;
  font-weight: bolder;
}
div input,
div textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-bottom: 6px;
  font-family: inherit;
}

div input:focus,
div textarea:focus {
  outline: none;
}
</style>
