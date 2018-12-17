<template>
    <div>
        <div>
            <participants-list :list="people"></participants-list>

        <h3>New participant</h3>
            <participants-form @added="addParticipants($event)"></participants-form>
        <form @submit.prevent="addNewParticipant()">
            <label>Firstname</label>
            <input type="text" v-model="newPerson.firstname">
            <label>Lastname</label>
            <input type="text" v-model="newPerson.lastname">
            <button>Add new participant</button>
        </form>
        </div>
    </div>
</template>

<script>
    import ParticipantsList from "./ParticipantsList.vue";
    import ParticipantsForm from "./ParticipantsForm.vue";
    export default {
        components: {ParticipantsList,ParticipantsForm},
        data() {
            return {
                newPerson: {firstname: '', lastname: ''},
                people: []
            };
        },
        methods: {
            addNewParticipant(participant) {
                if (!this.newPerson.lastname) {
                    return;
                }
                this.people.push(this.newPerson);
                this.newPerson = {};
            }
        }
    };
</script>


