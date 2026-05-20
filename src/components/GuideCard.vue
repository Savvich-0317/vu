<template>

<div class="card h-100">

    <img
        :src="guide.image"
        class="card-img-top"
    >

    <div class="card-body">

        <h5 class="card-title">
            {{ guide.title }}
        </h5>

        <p>
            {{ guide.level }}
        </p>


        <button
            class="btn btn-dark"
            @click="$emit('open-guide', guide)"
        >
            Read More
        </button>

    </div>

</div>

</template>

<script>
export default {

    props: {
        guide: Object
    }

}
</script>