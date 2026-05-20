<template>

<div
    v-if="guide"
    class="modal d-block"
    tabindex="-1"
>

    <div class="modal-dialog modal-lg">

        <div class="modal-content">

            <div class="modal-header">

                <h5 class="modal-title">
                    {{ guide.title }}
                </h5>

                <button
                    class="btn-close"
                    @click="$emit('close')"
                ></button>

            </div>

            <div class="modal-body">

                <img
                    :src="guide.image"
                    class="img-fluid mb-3"
                >

                <p>
                    {{ guide.text }}
                </p>

            </div>

        </div>

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