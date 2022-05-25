<!-- This component is used to show Markdown code block examples -->
<template lang="pug">
pre
  Markdown(:use="$slots.default" unwrap="p")
</template>
