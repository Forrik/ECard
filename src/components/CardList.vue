<template>
    <div class="wrapper_employee-card">
        
        <table class="card__table"  >
        <thead class="card__title">
            <td class="card__title__element">№</td>
            <td class="card__title__element">Имя</td>
            <td class="card__title__element">Фамилия</td>
            <td class="card__title__element">Отчество</td>
            <td class="card__title__element">email</td>
            <td class="card__title__element">Должность</td>
        </thead>
       
                <card-item
                 v-for="card in cards"
                 :card="card"
                 :key="card.id"
                 @remove="$emit('remove', card)"
                  />

    </table>
    </div>
</template>


<script>
import CardItem from './CardItem.vue';
    export default {
        components:{CardItem},
        props: {
            cards: {
                type: Array,
                required: true
            }
        }
        
        
    }
</script>

<style scoped>
.card__table {
   min-width: 100%; 
}

.card__title {
    display: flex;
    justify-content: space-between;
    margin: 20px;
}

.card__title__element {
    display: flex;
    justify-content: center;
    text-align: center;
    width: 7%;
    color:#526a7c;
}

.card__title__element:last-of-type {
    padding-right: 150px;
}



</style>