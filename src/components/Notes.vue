<template>
    <div class="note-div">
        <form @submit.prevent='addNote'>
            <label>Note Title</label>
            <input type="text" v-model='note.title'>
            <label>Note Text</label>
            <textarea v-model='note.text'></textarea>
            <button>Add Note</button>
        </form>
        <div class="wrapper">
            <div class='display' v-for='(note, index) in notes' :key='index'>
                <p>{{note.title}}</p>
                <small>{{note.date}}</small>
                <p>{{note.text}}</p>  
                <button class='muted-button' @click="removeNote">Remove</button>
           </div>
        </div>
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
            this.note = {
                title:'',
                text:''
            }
        },
        removeNote(index){
            this.notes.splice(index, 1)
        }
    }
}
</script>
<style scoped>
    .wrapper{
        display: flex;
        justify-content: space-around;
    }
    .display{
        width: 18rem;
        border: 1px solid grey;
        padding: 0.5rem;
    }
    @media screen and (max-width: 580px){
        .wrapper{
            display: block;
        }
        .display{
            width: 100%;
            margin: 0.5rem;
        }
    }
</style>