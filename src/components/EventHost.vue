<template>
  <div>
    <!-- trim修飾子 -->
    <!-- スペースが省略される。（前後のみ）ただし文字と文字の間は反応する -->
    <label for="host">主催者</label>
    <input
      id = "host"
      type="text"
      name="host"
      v-model.trim="eventData.host"
      >
    <p>{{ eventData.host }}</p>
  </div>
</template>
