<template>
    <div>
        <sectionCom />
        <facilities />
        <accommodation />
        <div class="wrap-about">
            <location />
            <contact />
            <footerCom />
        </div>
    </div>
</template>
<script>
import sectionCom from './sectionCom.vue'
import facilities from './facilities.vue'
import accommodation from './accommodation.vue'
import location from './location.vue'
import contact from './contact.vue'
import footerCom from './footerCom.vue'
export default {
    name: 'home',
    components: {
        sectionCom,
        facilities,
        accommodation,
        location,
        contact,
        footerCom,

    },
}
</script>
<style scoped>

</style>

