---
layout: default
title: Logout
permalink: /logout/
---

<!--  -->
logout
[logout]

logout
[logout]

<script>
  (function() {
    // Parse the user object from the document.cookie
    console.log(window.netlifyIdentity);
    if (window.netlifyIdentity) {
    window.netlifyIdentity.on("init", user => {
         if (user) {
             console.log(user);
             console.log(user.email);
             console.log("redirect");
             user.logout().then(
                response => window.location.href = '/',
                error => console.error("Failed to logout user: %o", error)
            );
              
           
         }
      if (!user) {
        window.netlifyIdentity.on("login", () => {
          document.location.href = "/index/";
        });
      }
    });
  }
  })();
</script>