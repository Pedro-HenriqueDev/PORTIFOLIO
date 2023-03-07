<script>
export default {
    props: {
        linkIcon: String,
        DelayMs: String
    }
}
</script>

<template>
    <img class="w-10" :class="DelayMs != undefined? `translate-y-10 icons-animated`: ``" :style="[DelayMs != undefined? `animation-delay:${DelayMs}ms;`: ``]" :src="linkIcon" />    
</template>

<style scoped>
.icons-animated {
  opacity: 0;
  animation: transform forwards alternate 500ms ease-in-out;
}

@keyframes transform {
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>