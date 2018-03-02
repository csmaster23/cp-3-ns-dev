<template>
  <div class="container">
    <div>
      <a target="_top" href="http://www.flamingtext.com/" ><img src="https://blog.flamingtext.com/blog/2018/03/01/flamingtext_com_1519939719_856800845.png" border="0" alt="Logo Design by FlamingText.com" title="Logo Design by FlamingText.com"></a>
    </div
    <br><br>
    <div class="row">
      <div class="col-lg-3 col-md-3 .d-none .d-sm-block .d-none .d-xs-block links" style="border: 3px solid #1E8BFF; max-height: 35vh; overflow: scroll">
      <h2>You might also like: </h2>
        <a href="https://tinder.com/?lang=en"><h3>Tinder</h3></a>
        <a href="https://mutualapp.co/"><h3>Mutual</h3></a>
        <a href="https://www.audiusa.com/?ds_kid=43700022088266026&CSREF=SEM%7C10770960%7C3118667%7C144106565%7C315947276%7C0&gclid=Cj0KCQiA5t7UBRDaARIsAOreQtihfJs820H6-4kFHL5v0o0mvbUNB8TfB_jcxupqXRX_eryvc66GjicaAoz8EALw_wcB&gclsrc=aw.ds"><h3>Audi</h3></a>
        <a href="http://www.thevillageatsouthcampus.com/"><h3>The Village</h3></a>
        <a href="https://www.vivint.com/ppc/brand?utm_medium=cpc&utm_term=vivint&utm_source=google&c_ps=s.google_k.vivint_m.e_n.g_po.1t1_ex._d.c&exid=117156&creative=&offer=&gclid=Cj0KCQiA5t7UBRDaARIsAOreQtjTsCQV45-5aMN2nHxr5rSVV5n4l5dFzski2nRFxDhHEEDJOFXDOzMaAv4uEALw_wcB"><h3>Vivint</h3></a>
        <a href="https://www.amazon.com/s/?ie=UTF8&keywords=white+snap+back+hat&tag=googhydr-20&index=aps&hvadid=229014731036&hvpos=1t1&hvnetw=g&hvrand=2163040130956501757&hvpone=&hvptwo=&hvqmt=b&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9060033&hvtargid=kwd-319052300602&ref=pd_sl_95msqa2fhy_b_p38"><h3>Snap Backs</h3></a>
        <a href="https://www.amazon.com/s/?ie=UTF8&keywords=tank+tops+men&tag=googhydr-20&index=apparel&hvadid=228966039104&hvpos=1t1&hvnetw=g&hvrand=11421760396093789814&hvpone=&hvptwo=&hvqmt=b&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9029857&hvtargid=kwd-296604948442&ref=pd_sl_93lowwtnbf_b_p38"><h3>Tool T's</h3></a>

      </div>
      <div class="col-lg-1 col-md-1 col-sm-1 col-xs-1"></div>
      <div class="col-lg-8 col-md-8 col-sm-8 col-xs-8" >
      <div class="row">
        <form v-on:submit.prevent="addComment">
          <input v-model="addedName" placeholder="Name" style="display: flex; width: 100%;"><br>
            <textarea v-model="addedComment"></textarea><br>
                <button type="button submit" class="btn btn-primary"> Post</button>
        </form>
      </div>

      <div v-for="comment in commentList" style="text-align: left; word-wrap: break-word;">
              <hr>
          	  <h3><div style="text-align: left">{{comment.name}}: {{comment.comment}}</div> <div></div></h3>
              <button type="button" class="btn btn-outline-primary" v-on:click ="addLike(comment.number)">Likes: {{comment.likes}}</button>

          	</div>
        <!--this is where the code for messenger goes-->
      </div>
    </div>
  </div>



</template>

<script>
 export default {
   name: 'Profile',
   data () {
     return {
      commentList: [],
      comment: 'hello world',
      addedName: '',
      addedComment: '',
      numLikes: 0,
      thisNum: 0,
      i: 0,
     }
   },
   methods:{
    addComment(){
      if (this.addedComment != ''){
        if (this.addedName === ''){
          this.addedName = 'Anonymous';
        }
        this.commentList.push({number: this.thisNum, name: this.addedName, comment: this.addedComment, likes: this.numLikes});
        this.addedName = '';
        this.addedComment = '';
        this.thisNum += 1;
      }
    },
    addLike(numbero){
      for(this.i = 0; this.i <this.commentList.length; this.i++){
        if(this.commentList[this.i].number === numbero){
          this.commentList[this.i].likes += 1;
        }
      }
      this.i = 0;

    }
   }
 }
</script>

<style scoped>
 img {
     max-width: 40vw;
     max-width: 40vh;
 }
.bText{
  font-weight: bold;
}
 a.active {
    color: gray;
 }

 a {
  color: black;
 }

 /*Hover state for top level links*/
 :hover a {

    color: black;

 }

.links {
  text-align: left;
    text-decoration: none;
    color: black;
}

h2 {
  font-size: 2vh;
  color: black;
}

</style>
