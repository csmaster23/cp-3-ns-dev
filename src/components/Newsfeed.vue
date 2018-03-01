<template>
  <div class="container">
    <div>
      <a target="_top" href="http://www.flamingtext.com/" ><img src="https://blog.flamingtext.com/blog/2018/03/01/flamingtext_com_1519939719_856800845.png" border="0" alt="Logo Design by FlamingText.com" title="Logo Design by FlamingText.com"></a>
    </div>
    <div class="row">
      <div class="col-lg-3 col-md-3 .d-none .d-sm-block .d-none .d-xs-block links" style="background-color: gray;">
      <h2>You might also like: </h2>
       
        <a href="https://tinder.com/?lang=en"><h3>Tinder</h3></a>
        <a href="https://mutualapp.co/"><h3>Mutual</h3></a>
        <a href="https://www.audiusa.com/?ds_kid=43700022088266026&CSREF=SEM%7C10770960%7C3118667%7C144106565%7C315947276%7C0&gclid=Cj0KCQiA5t7UBRDaARIsAOreQtihfJs820H6-4kFHL5v0o0mvbUNB8TfB_jcxupqXRX_eryvc66GjicaAoz8EALw_wcB&gclsrc=aw.ds"><h3>Buy another Audi</h3></a>
        <a href="http://www.thevillageatsouthcampus.com/"><h3>Renew your contract at The Village</h3></a>
        <a href="https://www.vivint.com/ppc/brand?utm_medium=cpc&utm_term=vivint&utm_source=google&c_ps=s.google_k.vivint_m.e_n.g_po.1t1_ex._d.c&exid=117156&creative=&offer=&gclid=Cj0KCQiA5t7UBRDaARIsAOreQtjTsCQV45-5aMN2nHxr5rSVV5n4l5dFzski2nRFxDhHEEDJOFXDOzMaAv4uEALw_wcB"><h3>Vivint</h3></a>
        <a href="https://www.amazon.com/s/?ie=UTF8&keywords=white+snap+back+hat&tag=googhydr-20&index=aps&hvadid=229014731036&hvpos=1t1&hvnetw=g&hvrand=2163040130956501757&hvpone=&hvptwo=&hvqmt=b&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9060033&hvtargid=kwd-319052300602&ref=pd_sl_95msqa2fhy_b_p38"><h3>Buy a Snap Back</h3></a>
        <a href="https://www.amazon.com/s/?ie=UTF8&keywords=tank+tops+men&tag=googhydr-20&index=apparel&hvadid=228966039104&hvpos=1t1&hvnetw=g&hvrand=11421760396093789814&hvpone=&hvptwo=&hvqmt=b&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9029857&hvtargid=kwd-296604948442&ref=pd_sl_93lowwtnbf_b_p38"><h3>Buy another Tool T</h3></a>
        

     
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <!--this is where the code for messenger goes-->
         <h3>Add a Comment</h3>
            <form v-on:submit.prevent="addComment">
              <input v-model="addedName" placeholder="Name"></p>
              <textarea v-model="addedComment"></textarea>
              <br/>
              <button type="submit">Comment</button>
            </form>
            <h3>Comments</h3>
            <div v-for="comment in comments[number]"> <!--notice the for loop -->
              <hr>
              <p>{{comment.text}}</p>
              <p><i>-- {{comment.author}}</i></p>
              <p>{{comment.timeStamp}}</p>
            </div>
      </div>

      <div class="col-lg-3 col-md-3 .d-none .d-sm-block .d-none .d-xs-block" style="background-color: gray;">
        <div class="likes">
      <h2> New to being a Provo Allstar? Here are some things all Provo Allstars like: </h2>
      <ul>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
        <li> {{}} </li>
      </ul>
      </div>
      </div>
    </div>
  </div>
  </div>
      

</template>

<script>
 export default {
   name: 'Profile',
   data () {
     return {
       

     }
   }
 }


    addComment: function() {
      if (!(this.number in this.comments))
       Vue.set(app.comments, this.number, new Array);

       var someDate = '';
       console.log("pre" + someDate);
       someDate = new Date();
       console.log("post " + someDate);
       var dd = someDate.getDate();
       var mm = someDate.getMonth() + 1;
       var yyyy = someDate.getFullYear();
       var sec = someDate.getSeconds();
       var min = someDate.getMinutes();
       var hours = someDate.getHours();

       if(dd<10) {
         dd = '0'+dd;
       }

       if(mm<10) {
         mm = '0'+mm;
       }

       if(sec<10) {
         sec = '0'+sec;
       }

       if(min<10) {
         min = '0'+ min;
       }

       if(hours<10) {
         hours = '0'+hours;
       }

       var formattedDate = dd + '/' + mm + '/' + yyyy + " @ " + hours + ':' + min + ":" + sec + " Military Time.";

      this.comments[this.number].push({author:this.addedName,text:this.addedComment,timeStamp:formattedDate});
      this.addedName = '';
      this.addedComment = '';
    },
 
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