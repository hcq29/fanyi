<template>
  <div class="row" id="translateFrom">
    <div class="jumbotron">
      <form class="form-inline my-2 my-lg-0" v-on:submit="formSubmit">
        <input class="form-control" type="text" placeholder="输入您的内容" v-model="textToTranslate" />
        <select class="form-control" v-model="language">
          <option selected value="en">Engilsh</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Janpenese</option>
          <option value="am">Amharic</option>
          <option value="fi">Finnish</option>
          <option value="ja">Janpenese</option>
          <option value="jv">Javanese</option>
          <option value="bn">Bengali</option>
          <option value="ro">Romanian</option>
          <option value="ml">Malayalam</option>
          <option value="ko">Korean</option>
          <option value="bg">Bulgarian</option>
          <option value="de">German</option>
        </select>
        <input class="btn btn-primary" type="submit" value="翻译" />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "translateFrom",
  data: function() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  methods: {
    formSubmit: function(e) {
      if (this.language)
        this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
};
</script>

<style>
#translateFrom {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
