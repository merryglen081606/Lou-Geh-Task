<template>
  <div class="notes__layout">

    <!-- CARD -->
    <div class="notes__holder" v-for="(data, n) in notes_list" :key="'n'+n">
      <div class="notes__note">
        <div class="notes__header">{{ data.title }}</div>
        <div class="notes__body">{{ data.desc }}</div>
        <div class="notes__footer">
        
          <input 
            type="button" 
            :value="data.status" 
            :class="`notes__button ${data.status == 'In Progress' ? 'notesEdit':'notesCommon'}`" 
            @click="changeStatus(n)">
        </div>
      </div>
    </div>

  </div>


</template>

<script>

export default {
data() {
  return {
    notes: [],
  }
},
methods: {
  changeStatus(key) {
    // console.log(key);
    this.$store.dispatch("change_status", {key: key});
  }
},
created() {
  // POPULATE notes ARRAY
  for(var x=0; x < 10; x++) {
    this.notes.push(
      {
        id: "n"+x,
        title: "Note no. "+x,
        desc: "Lorem Ipsum is simply dummy text of the xprinting and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
        status: "To Do"
      }
    );
  }

  // PUT DATA ON STATE notes
  this.$store.dispatch("store_notes", { notes: this.notes });

  // STORE notes ARRAY IN LOCAL STORAGE
  localStorage.notes = JSON.stringify(this.notes);

  // REVERT STRING TO ARRAY OBJECT
  // var temp = JSON.parse(localStorage.notes);
  // console.log(localStorage.notes);
  // console.log(tem{key: key}
},
computed: {
  statuss() {
    return this.$store.getters.getCardStatus;
  },
  notes_list() {
    return this.$store.getters.getNotes;
  }
}
}
</script>

<style>

</style>