<script setup lang="ts">
const props = defineProps<{
    name: string,
    coordinates: (number | undefined)[],
    category: string,
    id: string
}>()

const properties = ref({
    name: props.name,       
    category: props.category,
    id: props.id
})
</script>

<template>
    <ol-feature :properties="properties">
        <ol-geom-point :coordinates="props.coordinates"></ol-geom-point>
        <ol-style>
            <ol-style-icon :src="`/images/marks/${props.category}/${props.id}.svg`" :anchor="[0.2,1]"></ol-style-icon>
        </ol-style>
    </ol-feature>
</template>