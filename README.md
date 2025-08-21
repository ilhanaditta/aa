const user = "Admin";
    const pass = "123";

    if (localStorage.getItem("loginUser")) {
      showWelcome(localStorage.getItem("loginUser"));
    }

    function login() {
      const uname = document.getElementById("username").value;
      const pwd = document.getElementById("password").value;

      if (uname === user && pwd === pass) {
        localStorage.setItem("loginUser", uname);
        showWelcome(uname);
      } else {
        document.getElementById("errorMsg").classList.remove("hidden");
      }
    }

    function logout() {
      localStorage.removeItem("loginUser");
      document.getElementById("loginBox").classList.remove("hidden");
      document.getElementById("welcomeBox").classList.add("hidden");
      document.getElementById("errorMsg").classList.add("hidden");
    }

    function showWelcome(name) {
      document.getElementById("loginBox").classList.add("hidden");
      document.getElementById("welcomeBox").classList.remove("hidden");
      document.getElementById("welcomeUser").textContent = `Halo, ${name}`;
    }
