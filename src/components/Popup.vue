<template>
  <div class="text-center">
    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on }">
        <v-btn class="success" dark v-on="on">Add New Project</v-btn>
      </template>
<v-card>
<v-card-title class="headline grey lighten-2" primary-title>Add a New Project</v-card-title>
<v-card-text>
<v-form class="px-3" ref="form">
<v-text-field label="Title" v-model="title" prepend-icon="folder" :rules="inputRules"></v-text-field>
<v-textarea label="Information" v-model="content" prepend-icon="edit" :rules="inputRules"></v-textarea>

<v-menu max-width="290">
    <template v-slot:activator="{ on }">
        <v-text-field :rules="inputRules" :value="formattedDate" label="Due date" prepend-icon="mdi-calendar-range" v-on="on"></v-text-field>
    </template>
    <v-date-picker v-model="due"></v-date-picker>
</v-menu>

<v-spacer></v-spacer>

<v-btn flat class="success mx-0 mt-3" @click="submit">Add Project</v-btn>
</v-form>
</v-card-text>
</v-card>
    </v-dialog>
  </div>
</template>

<script>
	import format from 'date-fns/format'
	import parseISO from 'date-fns/parseISO'
export default {
name: 'Popup',
data() {
return {
title: '',
content: '',
due: null,
inputRules: [
v => v.length >= 3 || 'Minimum length is 3 characters'
]
}
},
methods: {
submit()
{
if(this.$refs.form.validate()) {
console.log(this.title, this.content)
}
}
},
computed: {
formattedDate(){
return this.due ? format(parseISO(this.due), 'do MMM yyyy') : ''
},

}

}
</script>