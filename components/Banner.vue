<template>
  <section class="banner-two" id="banner">
    <span class="banner-two__shape-1"></span>
    <span class="banner-two__shape-2"></span>
    <span class="banner-two__shape-3"></span>
    <span class="banner-two__shape-4"></span>
    <div class="banner-two__moc">
        <img src="/assets/images/mocs/banner-moc-1-1.jpg" style="height: 35%;width: 35%;border-radius: 50px;margin-left: 40%;margin-bottom: 10%;"   alt="Awesome Image" />
         </div><!-- /.banner-two__moc -->
    <div class="container">
      <div class="row">
        <div class="col-xl-6 col-lg-8">
          <div class="banner-one__content">
            <h3 class="banner-one__title">独属于 <br> <span>一个魂儿</span> 的 <br> App</h3><!-- /.banner-one__title -->
            <p class="banner-one__text">"一个魂儿"系A-SOUL女子偶像团体粉丝名 <br> 本app非商业用途，仅提供A-soul及相关社区服务 <br> 官方B站：《A-SOUL_Official》、抖音：《五个魂儿啊》</p>
            <!-- /.banner-one__text -->
            <div   class=" banner-one__btn thm-btn " @click="scrollPage()"  >
              <span>扫码下载</span>
              </div><!-- /.thm-btn -->
                <img class="banner-one_image" src='/assets/images/resources/asasfansdownload(6).png'/>
            </div><!-- /.banner-one__content -->
        </div><!-- /.col-lg-6 -->
      </div><!-- /.row -->
    </div><!-- /.container -->
    
  </section>
</template>

<script>
    export default {
      name: "BannerTwo",
       methods: {
		    scrollPage(){ 
          //index与循环的index对应可自由设置动态获取
        const PageId = document.querySelector('#pricing' )
        PageId.scrollIntoView({ behavior:"smooth", block: "center", inline: "start"})
      }

    }
    }
</script>


<style scoped>

</style>
