<template>
<div class="notes-section">
    <div class="columns">
        <div class="column has-text-centered">
            <strong>Notes</strong>
            <!-- <div v-for="note in notes" class="notes">{{note}}</div> -->
        </div>
        <div class="column has-text-centered">
            <strong>Timestamp</strong>
            <!-- <div v-for="timestamp in timestamps" 
            class="timestamps">{{ timestamp }}</div> -->
        </div>
    </div>
     <input type="text" class="input is-small" 
     @add-note="addNote"
     :placeholder="placeholder"
     v-model="input"
     @keyup.enter="monitorEnterKey"
     />
</div>
   
</template>

<script>
export default {
    name:'CustomEvents',
    data() { 
        return {
        notes: [],
        timestamps: [],
        placeholder: 'Enter a note',
        input:''
        }
    },
    methods: {
        monitorEnterKey() {
            this.$emit('add-note',{
                note: this.input,
                timestamp: new Date().toLocaleString()
            });
            this.input='';
        },
        addNote(event) {
            this.notes.push(event.note);
            this.timestamps.push(event.timestamp);
        }
    }
}
</script>

<style lang="scss" scoped>
    .notes-section {
        margin-top: 100px;
    width: 500px;
    }

    .columns {
    width: 100%;
    }

    .notes, .timestamps {
    padding: 5px 0px;
    }

    .note-count {
    margin-top: 48px;
    }

</style>
