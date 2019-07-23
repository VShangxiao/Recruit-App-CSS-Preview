# 原生 CSS 实现招聘App移动端效果

## 01-基础项目结构搭建

> Tips：安装 live server 插件，编辑器内预览效果

## 01版项目架构

![](C:\Web\Node\ZhiPin_CSS\01-架构.png)

### index.html

```
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>BOSS直聘</title>
  <link rel="stylesheet" href="./style/main.css">
</head>
<body>
  <div class="container">
    <div class="home-header">
      <img src="./images/home-search-text.png" alt="">
      <form action="">
        <input type="text" placeholder="搜索职位/公司">
        <button>搜索</button>
      </form>
    </div>
    <div class="home-categories">
      <dl>
        <dt>
          <img src="./images/technology.png" alt="">
          <div>技术</div>
        </dt>
        <dd>
          <a href="" class="tag">Java</a>
          <a href="" class="tag">PHP</a>
          <a href="" class="tag">Web前端</a>
          <a href="" class="tag">数据挖掘</a>
          <a href="" class="tag">Python</a>
          <a href="" class="tag">C++</a>
          <a href="" class="tag">iOS</a>
          <a href="" class="tag">Android</a>
        </dd>
      </dl>
    </div>
    <div class="home-footer">
        <p>违法和不良信息举报邮箱：jubao@kanzhun.com</p>
        <p>企业服务热线和举报投诉：400 065 5799</p>
    </div>
  </div>
</body>
</html>
```

### main.css

```
body {
  margin: 0;
  font-family: Arial, Helvetica, 'Microsoft Yahei', sans-serif;
}

.home-header {
  background: url('../images/home-bg.png') no-repeat;
  background-size: 100%, auto;
  text-align: center;
  padding-bottom: 1.5rem;
}

.home-header > img {
  width: 65%;
  margin: 2rem;
}

.home-header form {
  background: white;
  width: 90%;
  margin: 0 auto;
  line-height: 2.2rem;
  border-radius: 2.2rem;
}

.home-header form input {
  width: 75%;
  border: none;
  color: #aeaeae;
}

.home-header form button {
  font-size: 0.9rem;
  color: #5bd4c7;
  font-weight: lighter;
  border: none;
  background-color: #fff;
}
```

