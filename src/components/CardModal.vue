<template>
    <div class="card__popup">
        <div class="popup__item">
            <div>
                <img  src="https://via.placeholder.com/250x200" alt="">
            </div>
            <div>
                <form @submit.prevent>
                    <my-input v-model:value="card.firstName" placeholder="Имя" />
                    <my-input v-model:value="card.lastName" placeholder="Фамилия" />
                    <my-input v-model:value="card.secondName" placeholder="Отчество" />
                    
                    <my-button @click="createCard">Добавить</my-button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>

    export default {
        components: {
          
        },
        data () {
            return {
                card: {
                    lastName: '',
                    firstName: '',
                    secondName: ''
                }
            }
        },
        methods: {
            createCard() {
            this.card.id = Date.now().toString().slice(-4);
            this.$emit('create', this.card)
            this.card = {
                lastName: '',
                firstName: '',
                secondName: ''
            }
            }
           
        }
    }
</script>

<style scoped>

.card__popup {

}


.popup__item {
    background-color: white;
    border-radius: 25px;
    position: absolute;
    top: 20%;
    left: 25%;
    z-index: 3;
    width: 1000px;
    height: 600px;
    padding: 20px;
}
</style>