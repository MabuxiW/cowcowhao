# cowcowhao -- base.html -- repaired
<!doctype html>
<html lang="zh-cn">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.4.1/dist/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    <link rel="stylesheet" type="text/css" href="../static/CSS/base_additional.css"/>
    <link rel="SHORT ICON" href="../static/image/favicon.ico">
    <title>SGM-DE 尺寸工程！</title>
  </head>
  <body>

<!--调用Bootstrap Navbar-->
<nav class="navbar fixed-top navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="{% url 'index' %}">DE</a>        <!--设置点击DE图标回到主页，href中返回home url-->
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
            <li class="nav-item active" style="margin:0 10px;">
                <a class="nav-link" href=" {% url 'home' %}">Staff <span class="sr-only">(current)</span></a>
            </li>

            <li class="nav-item dropdown" style="margin:0 10px;">
                <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                Project
                </a>

                <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                    <a class="dropdown-item" href="#">Gloabl Project</a>
                    <a class="dropdown-item" href="#">Local Project</a>
                    <div class="dropdown-divider"></div>    <!--分割线-->
                    <a class="dropdown-item" href="#">Something else here</a>
                </div>
            </li>

            <li class="nav-item dropdown" style="margin:0 10px;">
                <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                Issue
                </a>

                <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                    <a class="dropdown-item" href="{% url 'onepage'%}">OnePage</a>
                    <a class="dropdown-item" href="{% url 'LessonsLearn'%}">L&L</a>
                    <div class="dropdown-divider"></div>    <!--分割线-->
                    <a class="dropdown-item" href="#">Other</a>
                </div>
            </li>

            <li class="nav-item" style="margin:0 10px;">
                <a class="nav-link" href="#">Reference</a>
            </li>

            <li class="nav-item" style="margin:0 10px;">
                <a class="nav-link" href="http://127.0.0.1:8000/admin/">后台管理</a>
            </li>

            <!--<li class="nav-item" style="margin:0 10px;">-->
                <!--<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>-->
            <!--</li>-->
        </ul>

        <!--登陆-->

            <!--<ul class="navbar-nav mr-auto">-->
                <!--<li class="nav-item" style="margin:0 10px;">-->
                    <!--<a class="nav-link" href="http://127.0.0.1:8000/admin/">登陆</a>-->
                <!--</li>-->

            <!--搜索功能-->

                  <form class="form-inline my-2 my-lg-0" method="POST" action="{% url 'user'%}"> <!--action内是将form内包裹的信息传递至后端所在的地址,此处是相对地址，即在该app中找到这个url文件，把数据传给这个地址，并在这个页面显示收到的数据-->
                      {% csrf_token %}
                    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search" name="username"><!--加入name是为了在urls后端拿到POST中输入框请求的数据-->
                    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">搜索</button>
                  </form>
    </nav>

    <br>
<!--<div class="container">-->
    {% block content %}
    {% endblock %}
<!--</div>-->


<footer class="text-muted">
    <br>
    <div class="container">
        <p class="float-right">
            <a href="#">Back to top</a>
        </p>
        <p> Welcome to Manufacturing Engineering - Dimension Engineering. </p>
        <p>Any Question? Please Contact Us by <a href="https://v4.bootcss.com/">Phone</a> or  <a href="/docs/getting-started/introduction/">Email</a>.</p>
    </div>
</footer>
    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/jquery@3.4.1/dist/jquery.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.4.1/dist/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>
  </body>
</html>
