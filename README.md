# login_website
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>تسجيل الدخول</title>
    <link rel="stylesheet" type="text/css" href="login.css">
   
  </head>
  <body>
    <div class="wrapper">
      <form class="" action="index.html" method="post">
        <div id="username_block">
          <label title="" for="username">اسم المستخدم</label>
          <input type="text" id="username" name="username"
          maxlength="10"
          onkeypress="doClear(this)"
          onblur="checkIfEmpty(this)"
          placeholder="اسم المستخدم لا يزيد عن 10 احرف">
        </div>

        <div id="pass_block">
          <label for="password">كلمة المرور</label>
          <input type="password" onkeypress="doClear(this)"
          id="password" name="password" onblur="checkIfEmpty(this)">
        </div>
        <div>
          <input type="checkbox"> تذكرني
        </div>
        <input type="button"
        onmouseout="this.style.backgroundColor='#630606'"
        onmouseover="this.style.backgroundColor='#003366'"
        value="دخول" id="do_login" onclick="doCheck()">
        <!-- <input type="submit" value="دخول">
        <button>دخول</button> -->
      </form>
    </div><!-- wrapper -->

    <script type="text/javascript">

    function checkIfEmpty(input)
    {
      if(input.value == '')  {
        input.style.border = '1px solid red';
      } else {
          input.style.border = '1px solid #ccc';
      }
    }

    function doClear(input)
    {
      var parent = input.parentNode;
      if(parent.lastChild.className == 'error')
      {
        parent.lastChild.remove();
        return;
      }

    }
    function doCheck()
    {
        var username = document.getElementById('username');
        var password = document.getElementById('password');
        if(username.value == '') {
          //alert('Please enter username');
          var s = document.createElement('span');
          var t = document.createTextNode('الرجاء كتابة اسم المستخدم');
          s.appendChild(t);
          s.setAttribute('class','error');
          document.getElementById('username_block').appendChild(s);
          return false;
        }

        if(password.value == '') {
          //alert('Please enter password');
          var p = document.createElement('span');
          var pass= document.createTextNode('أدخل كلمة المرور');
          p.appendChild(pass);
          p.setAttribute('class','error');
          document.getElementById('pass_block').appendChild(p);
          return false;
        }
    }

    </script>
  </body>
</html>
