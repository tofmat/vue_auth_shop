<template>
    <ul class="list-group">
        <li class="list-group-item" v-for="item in items" :key="item.id">
            {{item.name}} -$ {{item.price}} 
            <button @click="$emit('remove-from-cart', item)" class="btn badge badge-danger float-right">Remove from Cart</button>
        </li>
    </ul>
</template>

<script>
export default {
    props: ["items"]
}
</script> 