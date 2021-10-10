<template>

        <div class="filter">
            <div class="item" @click="filter('')">
            Borrador
            </div>
            <div class="item" @click="filter('Alive')">
            Alive
            </div>  
            <div class="item" @click="filter('Dead')">
            Dead
            </div>
            <div class="item" @click="filter('unknown')">
            Desconocido
            </div>    
        </div>
</template>

<script>
import {useStore} from 'vuex'
export default {
    setup() { 
        const store = useStore()

        const filter = ((status) => {
            store.dispatch('filterByStatus', status)
        })

        return {
            filter
        }
    }
}

</script>

<style lang="css">

    .filter {
        width: 400px;
        background: #eb94d0;
        padding: 15px;
        margin: 0 auto;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        border-radius: 30px;
       
        .item {
            padding: 1rem 0.5rem;
            background-color: var(--background-card);
            text-align: center;
            cursor: pointer;
            &:hover {
                color: var(--text-orange);
            }
        }
    }


</style>
