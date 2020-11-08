<template>
     <div id="app">
          <nav class="navbar navbar-expand-sm navbar-dark bg-dark">
               <a class="navbar-brand" href="#">Exams are bad</a>
               <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarsExample03" aria-controls="navbarsExample03" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
               </button>

               <div class="collapse navbar-collapse" id="navbarsExample03">
                    <ul class="navbar-nav mr-auto">
                         <li class="nav-item active">
                              <a class="nav-link active" href="#" >Wireless Networking <span class="sr-only">(current)</span></a>
                         </li>
                         <!-- <li class="nav-item">
                              <a class="nav-link" href="#">Link</a>
                         </li>
                         <li class="nav-item">
                              <a class="nav-link disabled" href="#">Disabled</a>
                         </li>
                         <li class="nav-item dropdown">
                              <a class="nav-link dropdown-toggle" href="http://example.com" id="dropdown03" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</a>
                              <div class="dropdown-menu" aria-labelledby="dropdown03">
                                   <a class="dropdown-item" href="#">Action</a>
                                   <a class="dropdown-item" href="#">Another action</a>
                                   <a class="dropdown-item" href="#">Something else here</a>
                              </div>
                         </li> -->
                    </ul>
                    <!-- <form class="form-inline my-2 my-md-0">
                         <input class="form-control" type="text" placeholder="Search" />
                    </form> -->
               </div>
          </nav>

          <div style="display:flex; margin:20px">
               <div style="margin-right:100px">
                    <CCC />
               </div>
               <div style="margin-right:100px">
                    <FSLC />
               </div>
               <div>
                    <SineWave />
               </div>
          </div>
     </div>
</template>

<script>
import CCC from './components/CCC.vue';
import FSLC from './components/FSLC.vue';
import SineWave from './components/SineWave.vue'
export default {
     name: 'app',
     components: {
          CCC,
          FSLC,
          SineWave
     },
};
</script>

<style></style>
