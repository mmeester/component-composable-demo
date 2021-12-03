<template>
  <div class="component__inside">
    <example-component />
  </div>
  
  <div class="component__outside">
    <h2>
      uiState outside Component: {{ uiState}}
    </h2>
    
    Why is the example component not updated by the button below?<br />
    <button @click="uiState = 'Changed outside component'">Change outside component</button>
  </div>
</template>

<script setup>
import { useExampleComposable } from 'component-composable';

// why is this a different ui state than the state inside <example-component />?
const { uiState } = useExampleComposable();
</script>

<style>
.component__inside { 
  border: 1px solid red;
  margin-bottom: 1rem;
}

.component__outside {
  border: 1px solid green;
}
</style>
