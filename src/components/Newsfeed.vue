<template>
  <div class="container">
    <div>
      <a target="_top" href="http://www.flamingtext.com/" ><img src="https://blog.flamingtext.com/blog/2018/03/01/flamingtext_com_1519939719_856800845.png" border="0" alt="Logo Design by FlamingText.com" title="Logo Design by FlamingText.com"></a>
    </div>
    <div class="row">
      <div class="col-lg-3 col-md-3 .d-none .d-sm-block .d-none .d-xs-block">
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <h3>Add a Comment</h3>
        <form v-on:submit.prevent="addComment">
        <input v-model="addedName" placeholder="Name"></p>
        <textarea v-model="addedComment"></textarea>
        <br/>
        <button type="submit">Comment</button>
        </form>
        <h3>Comments</h3>
        <div v-for="comment in comments[number]">
        <hr>
        <p>{{comment.text}}</p>
        <p><i>-- {{comment.author}}</i></p>
        <p>{{comment.today}}</p>
      </div>
      <div class="col-lg-3 col-md-3 .d-none .d-sm-block .d-none .d-xs-block">
      </div>
    </div>
  </div>
  </div>
      

</template>

<script>
  export default {
     name: 'Newsfeed',
     data () {
        return {
          addedName: '',
          addedComment: '',
          date: '',
          comments: {},
        }  
     }, // close data

      methods () {
        todayDate: function() {
          var today = new Date();
          var hour = today.getHours();
          var minute = today.getMinutes();
          var dd = today.getDate();
          var mm = today.getMonth()+1;
          var yyyy = today.getFullYear();
          if(dd<10) {
            dd = '0'+dd
          }
          if(mm<10) {
            mm = '0'+mm
          }
          if (minute<10) {
            minute = '0'+minute
          }
          today = hour + ":" + minute + " on " + mm + '-' + dd + '-' + yyyy;
          return today;
        },
        addComment: function() {
          if (!(this.number in this.comments))
      Vue.set(app.comments, this.number, new Array);
          this.comments[this.number].push({author:this.addedName,today:this.todayDate(),text:this.addedComment});
          this.addedName = '';
          this.addedComment = '';
        }

      
 } //close export
 
</script>

<style scoped>
 img {
     max-width: 40vw;
     max-width: 40vh;
 }
.bText{
  font-weight: bold;
}
 .quals{
  text-align:left;
 }


</style>