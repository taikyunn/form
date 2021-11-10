<template>
  <div id="app">
    <h1>イベントフォーム</h1>
    <!-- eventdata.titleでデータを渡している -->
    <EventTitle v-model="eventData.title"></EventTitle>
    <!-- 上記の中身は下記と同じ -->
    <!-- <EventTitle
      :value="eventData.title"
      @input="eventData.title = $event"
    >
    </EventTitle> -->

    <label for="number">最大人数</label>
    <!-- number修飾子 -->
    <!-- type="number"の場合、初期値はtype:numberだが値が変更されるとtype:stringになる -->
    <!-- 値が変更されてもtype:numberとするにはv-model.numberと設定すること。 -->
    <input
      id = "maxNumber"
      type="number"
      name="number"
      v-model.number="eventData.maxNumber"
    >
    <!-- typeofをつけることで値の型を調べることができる -->
    <p>{{ typeof eventData.maxNumber }}</p>

  <!-- <EventHost v-model="eventData.host"></EventHost> -->

    <!-- 複数行バインド -->
    <!-- texaareaにvmodelをつければ使用できる -->
    <label for="detail">イベントの内容：</label>
    <textarea
      id ="detail"
      name="detail"
      v-model="eventData.detail"
      ></textarea>
      <!-- preは改行を正しく表示してくれる -->
      <pre>{{eventData.detail}}</pre>


    <!-- チェックボックスのバインド -->
    <!-- 単体のチェックボックスの場合 -->
    <!-- ポイント：初期値はbool型で指定する -->
    <input
      type="checkbox"
      id="isPrivate"
      v-model="eventData.isPrivate"
    >
    <label for="isPrivate">公開</label>
    <p>{{ eventData.isPrivate }}</p>


    <!-- チェックボックスのバインド -->
    <!-- 複数のチェックボックスの場合 -->
    <!-- ポイント：初期値は配列で指定すること。 -->
    <p>参加条件</p>
    <input
      id="10"
      type="checkbox"
      value="10代"
      v-model="eventData.target"
    >
    <label for="10">10代</label>
    <input
      id="20"
      type="checkbox"
      value="20代"
      v-model="eventData.target"
    >
    <label for="20">20代</label>
    <input
      id="30"
      type="checkbox"
      value="30代"
      v-model="eventData.target"
    >
    <label for="30">30代</label>
    <input
      id="40"
      type="checkbox"
      value="40代"
      v-model="eventData.target"
    >
    <label for="40">40代</label>

    <p>{{eventData.target}}</p>

    <!-- ラジオボタンのバインド -->
    <!-- 初期値はvalueを指定すればOK-->
    <input
      type="radio"
      id="free"
      value="無料"
      v-model="eventData.price"
    >
    <label for="free">無料</label>

    <input
      type="radio"
      id="paid"
      value="有料"
      v-model="eventData.price"
    >
    <label for="paid">有料</label>
    <p>{{eventData.price}}</p>
    <br>

    <!-- セレクトボックスのバインド -->
    <!-- selectタグにv-modelをつける -->
    <!-- multiple:複数選択可のselectボックスが作れる -->
    <select v-model="eventData.location" multiple>
      <option
        v-for="location in locations"
        :key="location">
        {{location}}
      </option>
    </select>
    <p>{{eventData.location}}</p>
  </div>
</template>

<script>
import EventTitle from './components/EventTitle.vue'
// import EventHost from './components/EventHost.vue'

export default {
  components: {
    EventTitle,
    // EventHost,
  },
  data() {
    return {
      locations: ['東京','大阪', '名古屋'],
      eventData: {
        title: '',
        maxNumber: 0,
        host: '',
        detail:'',
        isPrivate: false,
        target: [],
        price: '無料',
        location: [],
      }
    }
  }
}
</script>
