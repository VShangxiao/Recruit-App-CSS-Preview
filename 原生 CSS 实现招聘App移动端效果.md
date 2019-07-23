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

# 02-dl内容架构设计

index.html

```
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>BOSS直聘 - 互联网招聘神器</title>
  <link rel="stylesheet" href="./style/main.css">
  <link rel="shortcut icon" type="./images/favicon.png">
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
          <a href="" class="tag">Go</a>
          <a href="" class="tag">Python</a>
          <a href="" class="tag">iOS</a>
        </dd>
      </dl>
      <dl>
        <dt>
          <img src="./images/product.png" alt="">
          <div>产品</div>
        </dt>
        <dd>
          <a href="" class="tag">产品运营</a>
          <a href="" class="tag">产品经理</a>
          <a href="" class="tag">Web产品经理</a>
          <a href="" class="tag">数据产品经理</a>
        </dd>
      </dl>
      <dl>
        <dt>
          <img src="./images/operate.png" alt="">
          <div>运营</div>
        </dt>
        <dd>
          <a href="" class="tag">客户运营</a>
          <a href="" class="tag">电商运营</a>
          <a href="" class="tag">商家运营</a>
          <a href="" class="tag">运营总监</a>
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

main.css

```
body {
  margin: 0;
  font-family: Arial, Helvetica, 'Microsoft Yahei', sans-serif;
  color: #7e8793;
  -webkit-font-smoothing: antialiased;
}

.home-header {
  background: url('../images/home-bg.png') no-repeat;
  background-size: 100%, auto;
  text-align: center;
  padding-bottom: 1.5rem;
}

.home-header > img {
  width: 67%;
  margin: 2.3rem;
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
  font-size: 0.85rem;
  outline: none;
}

.home-header form button {
  font-size: 0.9rem;
  color: #5bd4c7;
  border: none;
  background-color: #fff;
}

.home-categories {
  padding: 0 1rem;
}

.home-categories dt {
  display: flex;
  align-items: center;
  color: #525252;
}

.home-categories dt img {
  height: 3rem;
  margin-right: 1rem;
}

.home-categories dd {
  margin: 0;
  margin: 0 -0.4rem;
}

.home-categories dd .tag {
  background: #f5f8f9;
  color: #7e8793;
  font-size: 13px;
  padding: 0.3rem 1rem;
  margin: 0 8px 8px 0;
  display: inline-block;
  border-radius: 100px;
  text-decoration: none;
}

.home-footer {
  width: 80%;
  margin: 0 auto;
  font-size: 12px;
}

.home-footer p {
  margin: 0.2rem 0;
}
```

# 03-列表页设计

![](C:\Web\Node\ZhiPin_CSS\02-架构.png)

list.html

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>【北京web前端招聘】2019年北京web前端最新人才招聘信息-BOSS直聘</title>
  <link rel="stylesheet" href="style/main.css">
</head>
<body>
  <div class="container">
    <div class="list-header">
      <img src="./images/icon-home.png" alt="">
      <form action="">
        <div class="inner">
          <input type="text">
          <span>&times;</span>
        </div>
        <button>搜索</button>
      </form>
    </div>

    <div class="filter">
      <dl class="active">
        <dt>经验</dt>
        <dd>
          <li class="active">不限</li>
          <li>应届生</li>
          <li>一年以内</li>
          <li>1-3年</li>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <li>不限</li>
          <li>应届生</li>
          <li>一年以内</li>
          <li>1-3年</li>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <li>不限</li>
          <li>应届生</li>
          <li>一年以内</li>
          <li>1-3年</li>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <li>不限</li>
          <li>应届生</li>
          <li>一年以内</li>
          <li>1-3年</li>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <li>不限</li>
          <li>应届生</li>
          <li>一年以内</li>
          <li>1-3年</li>
        </dd>
      </dl>
    </div>
  </div>
  <ul class="job-list">
    <li>
      <a href="">
        <img src="./images/company-logo.jpg" alt="">
        <div class="text">
          <div class="title">
            web前端
            <span class="salary">11-17K·13薪</span>
          </div>
          <div class="company">
            京东集团
          </div>
          <div class="props">
            <span>北京</span>
            <span>1-3年</span>
            <span>本科</span>
          </div>
        </div>
      </a>
    </li>
  </ul>

</body>
</html>
```

