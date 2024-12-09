<!-- Komponent som hanterar ikonrelaterad logik-->

<!-- Ikontemplate-->
<template>
    <span
    class="inline-flex"
    :class="[sizeClass, colorClass]"
    v-html="iconSvg"></span>
</template>

<!-- Inhämtning av ikonsamlingen. Skapar samlingar av storleks- och färgalternativ. Skapar tre properties för ikonerna; namn, size och color -->
<script>
import {Icons} from "../assets/icons";

const IconSizes = {
    sm: 'w-4 h-4',
    md: 'w-6 h-6',
    lg: 'w-8 h-8',
    xl: 'w-10 h-10'
    };

const IconColors = {
    current: 'text-current',
    prim: 'text-blue-500',
    sec: 'text-purple-500',
    gray: 'text-gray-500'
    };

export default {
    name: "Icon",
    props: {
        name: {
            type: String
        }, 
        size: {
            type: String, 
            default: 'md', //Finns som alternativ; sm (16px), md (24px), lg (32px), xl(40px)

        }, 
        color: {
            type: String,
            default: "current" //Finns som alternativen: Current, prim (blue-500), sec (purple-500) & gray (gray-500)
        }
    },
    
    computed: {
        iconSvg() {//Tar namn som property, hittar matchande ikon.svg från Icons-objektet. Returnerar en tom string om objektet inte kan hittas.
            return Icons[this.name] || '';
        }, 
        sizeClass(){ 
            return IconSizes[this.size];
        }, 
        colorClass(){
            return IconColors[this.color];
        }

    }
};
</script>

<style scoped>
span :deep(svg){
    @apply w-full h-full;
}
</style>