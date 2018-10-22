<template>
         <button class="g-button" :class="{[position]: true}">
             <svg v-if="icon" class="icon">
                 <use :xlink:href=`#i-${icon}`></use>
             </svg>
             <div class="content">
                 <slot></slot>
             </div>
         </button>
</template>
<script>
    export  default  {
      props: ['icon', 'position']
    }
</script>
<style lang="scss">
    .g-button {
        display: flex;
        align-items: center;
        font-size: var(--font-size);
        height: var(--button-height);
        padding: 0 1em;
        border-radius: var(--border-radius);
        border: 1px solid var(--border-color);
        background: var(--button-bg);
        &:hover {
            border-color: var(--border-color-hover);
        }
        &:active {
            border-color: var(--button-active-bg);
        }
        &:focus {
            outline: none;
        }

    }
    .left {
         > .content {
             order: 2;
         }
         >.icon {
             order: 1;
         }
     }
    .right {
        > .content {
            order: 1;
        }
        > .icon {
            order: 2;
        }
    }
</style>