<template>
    <tbody  class="employee-card">
        <td class="card__element">№ {{card.id}} </td>
        <td class="card__element">{{ card.firstName }}</td>
        <td class="card__element">{{ card.lastName }}</td>
        <td class="card__element">{{ card.middleName }}</td>
        <td class="card__element">{{card.email}}</td>
        <td  class="card__element"> {{card.jobTitle}} </td>
        <div class="card__icons">
            <svg @click="$emit('remove', card)" class="card__icon" viewBox="0 0 24 24" fill="none">
                <path d="M10 11V17" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M14 11V17" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M4 7H20" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M6 7H12H18V18C18 19.6569 16.6569 21 15 21H9C7.34315 21 6 19.6569 6 18V7Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M9 5C9 3.89543 9.89543 3 11 3H13C14.1046 3 15 3.89543 15 5V7H9V5Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            <svg  class="card__icon" viewBox="0 0 24 24" fill="none">
                <path d="M3 12C3 4.5885 4.5885 3 12 3C19.4115 3 21 4.5885 21 12C21 19.4115 19.4115 21 12 21C4.5885 21 3 19.4115 3 12Z" stroke="#323232" stroke-width="2"/>
                <path d="M16 12L8 12" stroke="#323232" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M13 15L15.913 12.087V12.087C15.961 12.039 15.961 11.961 15.913 11.913V11.913L13 9" stroke="#323232" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
        </div>
        
        </tbody>
</template>

<script>
    export default {
        props: {
            card: {
                type: Object,
                required: true,
            }
        }
    }
</script>

<style scoped>
.employee-card {
    display: flex;
    justify-content: space-between;
    background-color: #fff;
    margin: 20px 0;
    padding: 15px;
    border-radius: 20px;
    min-width: 100%;
    position: relative;
}

.card__element {
    display: flex;
   text-align: center;
   justify-content: center;
   width: 7%;
   align-items: center;
}

.card__element:last-of-type {
    padding-right: 150px;
}

.employee-card:hover .card__icons{
    opacity: 1;
    transition: all .4s ease-in;
}

.card__icons {
    position: absolute;
    top: 25%;
    right: 20px;
    opacity: 0;
    cursor: pointer;
    display: flex;
    justify-content: space-around;
    width: 6%;
}

.card__icon {
    height: 30px;
    width: 30px;
    
}
</style>