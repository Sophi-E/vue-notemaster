<template>
    <div class="note-div">
        <form @submit.prevent='addNote'>
            <label>Note Title</label>
            <input type="text" v-model='note.title'>
            <label>Note Text</label>
            <textarea v-model='note.text'></textarea>
            <button>Add Note</button>
        </form>
    </div>
</template>
<script>
export default {
    name: 'note-div',
    data(){
        return{
            note: {
                title: '',
                text: ''
            },
            notes:[],
        }
    },
    methods:{
        addNote(){
            let {title, text} = this.note;
            this.notes.push({
                title,
                text,
                date: new Date(Date.now()).toLocaleString()
            })
            this.note = {}
        }
    }
}
</script>
<style>

</style>