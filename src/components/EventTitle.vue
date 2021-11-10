<template>
  <div>
    <label for="title">タイトル</label>
    <!-- v-modelの中身 -->
    <!-- v-modelの中身は下記二行になる。 -->
    <!-- 下記二行になるのはinput type="text"の場合のみ。 -->

    <!-- <input
      id = "title"
      type="text"
      name="title"
      v-model="eventData.title"

      :value="eventData.title"
      @input="eventData.title = $event.target.value"

      lazy修飾子の場合
      @change="eventData.title = $event.target.value"
    > -->

    <!-- コンポーネントでv-modelを使用する -->

    <!-- ②eventdata.titleをvalueに反映させる -->
    <!-- ③inputというイベントを発火させる。タイミングはinputイベントが発火した時。つまり値が入力された時。 -->
    <!-- ④第二引数のデータが実際に更新される値になる。。 -->
    <input
      id = "title"
      type="text"
      name="title"
      :value="value1"
      @input="$emit('input', $event.target.value)"
      >
    <p>{{ value }}</p>
  </div>
</template>

<script>
export default {
  // ①eventdata.titleを受け取る
  props: ["value1"]
}
</script> 
