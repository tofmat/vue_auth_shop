<template>
    <div>
        <ul class="list-group">
            <li class="list-group-item" v-for="item in items" :key="item.id">
                {{item.name}} -$ {{item.price}} 
                <button @click="$emit('remove-from-cart', item)" class="btn badge badge-danger float-right">Remove from Cart</button>
            </li>
        </ul>
        <div class="card p-3 my-5">
            <h4 class="text-center">$ {{ total }}</h4>
        </div>
        <button @click="$emit('pay')" class="button btn btn-info form-control">Pay Now</button>
    </div>
</template>
    
    
    <style>
    
    </style>
 
<script>
export default {
    props: ["items"],

    computed:{
        total(){
             return this.items.reduce((acc, item) => acc + Number(item.price), 0)
        }
    }
}
</script> 