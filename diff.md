diff --git a/css/style.css b/css/style.css
index daf730f..651c467 100644
--- a/css/style.css
+++ b/css/style.css
@@ -125,6 +125,11 @@ footer a {
   /* font-size: 2rem; */
 }
 
+#modal1 {
+  min-width: 100vw;
+  min-height: 100vh;
+}
+
 /*************************************** HEADER ***************************************/
 header {
   padding: 60px;
diff --git a/index.html b/index.html
index 7e2eefe..de0833d 100644
--- a/index.html
+++ b/index.html
@@ -47,7 +47,10 @@
         <div class="create">
           <a href="" class="btn z-depth-0">Create on Patreon</a>
         </div>
-        <a href="" data-target="modal1" class="hamburger black-text right"
+        <a
+          href="#"
+          data-target="modal1"
+          class="hamburger black-text modal-trigger right"
           ><i class="material-icons">menu</i></a
         >
       </div>
@@ -71,11 +74,6 @@
         <h4>Modal Header</h4>
         <p>A bunch of text</p>
       </div>
-      <div class="modal-footer">
-        <a href="#!" class="modal-close waves-effect waves-green btn-flat"
-          >Agree</a
-        >
-      </div>
     </div>
 
     <!-- header -->
@@ -448,7 +446,14 @@
       document.addEventListener("DOMContentLoaded", function () {
         //Hamburger menu (modal)
         let modal = document.querySelectorAll(".modal");
-        let instancesModal = M.Modal.init(modal);
+        let instancesModal = M.Modal.init(modal, {
+          inDuration: 0,
+          outDuration: 0,
+          startingTop: "0%",
+          endingTop: "0%",
+
+          preventScrolling: true,
+        });
 
         //Carousel
         let carousel = document.querySelector(".carousel");
