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

## index.html

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

## list.html

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

# 04-list页搭建框架(header完成)

## list.html

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
    <div class="list-header flex">
      <img src="./images/icon-home.png" alt="">
      <form action="" class="flex">
        <div class="inner flex">
          <input type="text" value="web前端">
          <span>&times;</span>
        </div>
        <button>搜索</button>
      </form>
    </div>

    <div class="filter flex">
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
      <a href="" class="flex">
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
  width: 92%;
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

/* list-page */
.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.list-header {
  padding: 0.8rem 1rem; 
}

.list-header img {
  height: 1.2rem;
}


.list-header form {
  width: 100%;
}

.list-header form .inner {
  width: 100%;
  background: #f5f8f9;
  margin: 0 1rem;
  line-height: 1.7rem;
  border-radius: 15px;
  padding: 0 1rem;
}

.list-header form .inner input {
  width: 80%;
  background: transparent;
  border: none;
  outline: none;
  color: #8b96a6;
}

.list-header form button {
  border: none;
  background: none;
  font-size: 0.9rem;
  color: #7e8793;
  flex-shrink: 0;
}
```

# 05

## list.html

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
    <div class="list-header flex">
      <img src="./images/icon-home.png" alt="">
      <form action="" class="flex">
        <div class="inner flex">
          <input type="text" value="web前端">
          <span>&times;</span>
        </div>
        <button>搜索</button>
      </form>
    </div>

    <div class="filter flex">
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
          <li >应届生</li>
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
      <a href="" class="flex">
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
  width: 92%;
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

/* list-page */
.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.list-header {
  padding: 0.8rem 1rem; 
}

.list-header img {
  height: 1.2rem;
}


.list-header form {
  width: 100%;
}

.list-header form .inner {
  width: 100%;
  background: #f5f8f9;
  margin: 0 1rem;
  line-height: 1.7rem;
  border-radius: 15px;
  padding: 0 1rem;
}

.list-header form .inner input {
  width: 80%;
  background: transparent;
  border: none;
  outline: none;
  color: #8b96a6;
}

.list-header form button {
  border: none;
  background: none;
  font-size: 0.9rem;
  color: #7e8793;
  flex-shrink: 0;
  padding: 0;
}

.filter {
  padding: 0.5rem 1rem;
  border: 1px solid #f5f8f9;

}

.filter dl, .filter dd {
  margin: 0;
}

.filter dt {
  font-size: 0.8rem;
}

.filter .active dt {
  color: #333;
}

.filter dt:after {
  content: '';
  display: inline-block;
  width: 4px;
  height: 4px;
  border: 1px solid #999;
  border-style: solid none none solid;
  transform: rotate(225deg);
  transform-origin: 2px 1px;
  margin-left: 0.5rem;
  transition: all 0.2s;

}

.filter .active dt:after {
  transform: rotate(45deg);
}

.filter dd {
  display: none;

}

.filter .active dd {
  display: block;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100vh;
  position: absolute;
  top: 90px;
  left: 0;
}

.filter .active dd ul {
  margin: 0;
  padding: 0;
  background: #fff;

}

.filter .active dd li {
  line-height: 3.5rem;
  text-indent: 1rem;
  color: #999;
}

.filter .active dd li.active {
  background: #f5f8f9;
  color: #333;
}
```

# 06-list页面基本完成

> ">" 是子选择符,用于匹配那些其他元素的直接后辈

## list.html

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
    <div class="list-header flex">
      <img src="./images/icon-home.png" alt="">
      <form action="" class="flex">
        <div class="inner flex">
          <input type="text" value="web前端">
          <span>&times;</span>
        </div>
        <button>搜索</button>
      </form>
    </div>

    <div class="filter flex">
      <dl class="active1">
        <dt>经验</dt>
        <dd>
          <ul>
            <li class="active">不限</li>
            <li>应届生</li>
            <li>一年以内</li>
            <li>1-3年</li>
          </ul>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <ul>
            <li class="active">不限</li>
            <li>应届生</li>
            <li>一年以内</li>
            <li>1-3年</li>
          </ul>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <ul>
            <li class="active">不限</li>
            <li>应届生</li>
            <li>一年以内</li>
            <li>1-3年</li>
          </ul>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <ul>
            <li class="active">不限</li>
            <li>应届生</li>
            <li>一年以内</li>
            <li>1-3年</li>
          </ul>
        </dd>
      </dl>
      <dl>
        <dt>经验</dt>
        <dd>
          <ul>
            <li class="active">不限</li>
            <li>应届生</li>
            <li>一年以内</li>
            <li>1-3年</li>
          </ul>
        </dd>
      </dl> 
    </div>
  </div>
  <ul class="job-list">
    <li>
      <a href="" class="job-item flex">
        <img src="./images/company-logo.jpg" alt="">
        <div class="text">
          <div class="title flex">
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
    <li>
      <a href="" class="job-item flex">
        <img src="./images/company-logo.jpg" alt="">
        <div class="text">
          <div class="title flex">
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
    <li>
      <a href="" class="job-item flex">
        <img src="./images/company-logo.jpg" alt="">
        <div class="text">
          <div class="title flex">
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
    <li>
      <a href="" class="job-item flex">
        <img src="./images/company-logo.jpg" alt="">
        <div class="text">
          <div class="title flex">
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
    <li>
      <a href="" class="job-item flex">
        <img src="./images/company-logo.jpg" alt="">
        <div class="text">
          <div class="title flex">
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

## main.css

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
  width: 92%;
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

/* list-page */
.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.list-header {
  padding: 0.8rem 1rem; 
}

.list-header img {
  height: 1.2rem;
}


.list-header form {
  width: 100%;
}

.list-header form .inner {
  width: 100%;
  background: #f5f8f9;
  margin: 0 1rem;
  line-height: 1.7rem;
  border-radius: 15px;
  padding: 0 1rem;
}

.list-header form .inner input {
  width: 80%;
  background: transparent;
  border: none;
  outline: none;
  color: #8b96a6;
}

.list-header form button {
  border: none;
  background: none;
  font-size: 0.9rem;
  color: #7e8793;
  flex-shrink: 0;
  padding: 0;
}

.filter {
  padding: 0.5rem 1rem;
  border: 1px solid #f5f8f9;

}

.filter dl, .filter dd {
  margin: 0;
}

.filter dt {
  font-size: 0.8rem;
}

.filter .active dt {
  color: #333;
}

.filter dt:after {
  content: '';
  display: inline-block;
  width: 4px;
  height: 4px;
  border: 1px solid #999;
  border-style: solid none none solid;
  transform: rotate(225deg);
  transform-origin: 2px 1px;
  margin-left: 0.5rem;
  transition: all 0.2s;

}

.filter .active dt:after {
  transform: rotate(45deg);
}

.filter dd {
  display: none;

}

.filter .active dd {
  display: block;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100vh;
  position: absolute;
  top: 90px;
  left: 0;
}

.filter .active dd ul {
  margin: 0;
  padding: 0;
  background: #fff;

}

.filter .active dd li {
  line-height: 3.5rem;
  text-indent: 1rem;
  color: #999;
}

.filter .active dd li.active {
  background: #f5f8f9;
  color: #333;
}

.job-list {
  margin: 0;
  padding: 0;
}

.job-item {
  margin: 1rem;
  padding-bottom: 1rem;
  color: #7e8793;
  text-decoration: none;
  border-bottom: 1px solid #f5f8f9;
}

.job-item > img {
  height: 3.5rem;
  border-radius: 0.3rem;
}

.job-item .text {
  width: 100%;
  margin-left: 1rem;
}

.job-item .title {
  font-size: 15px;
  color: #333;
}

.job-item .salary{
  font-size: 16px;
  color: #fc6c38;
}

.job-item .company {
  color: #333;
  font-size: 0.8rem;
  margin: 0.2rem 0;
}

.job-item .props {
  font-size: 0.8rem;
}

.job-item .props span {
  margin-right: 0.5rem; 
}
```

# 07-详情页布局

## detail.html

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>【web前端招聘】_京东集团招聘-BOSS直聘</title>
  <link rel="stylesheet" href="./style/main.css">
</head>
<body>
  <div class="container">
    <div class="top-bar flex">
      <img src="./images/logo.png" alt="">
      <form action="" class="flex">
        <input type="text" placeholder="搜索职位">
        <button class="search-icon"></button>
      </form>
    </div>
  </div>

  <div class="job-info">
    <div class="title flex">
      <span>web前端</span>
      <span class="salary">11-17K·13薪</span>
    </div>
    <div class="props">
      <div>
        北京 | 1-3年 | 本科
      </div>
      <div>
        更新于：2019年6月6日
      </div>
    </div>
    <div class="tags">
      <span>HTML/CSS</span>
      <span>前端开发</span>
      <span>Javascript</span>
    </div>
  </div>

  <div class="user-info flex">
    <img src="./images/avatar.png" alt="">
    <div>
      <div class="name flex">
        <span>高先生</span>
        <span>感兴趣</span>
      </div>
      <div>
        京东集团·招聘者
      </div>
    </div>
    <button class="btn">立即沟通</button>
  </div>

</body>
</html>
```

# 08-继续详情页

## detail.html

```
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>【web前端招聘】_京东集团招聘-BOSS直聘</title>
  <link rel="stylesheet" href="./style/main.css">
</head>

<body>
  <div class="container">
    <div class="top-bar flex">
      <img src="./images/logo.png" alt="">
      <form action="" class="flex">
        <input type="text" placeholder="搜索职位">
        <button class="search-icon"></button>
      </form>
    </div>
  </div>

  <div class="job-info">
    <div class="title flex">
      <span>web前端</span>
      <span class="salary">11-17K·13薪</span>
    </div>
    <div class="props">
      <div>
        北京 | 1-3年 | 本科
      </div>
      <div>
        更新于：2019年6月6日
      </div>
    </div>
    <div class="tags">
      <span>HTML/CSS</span>
      <span>前端开发</span>
      <span>Javascript</span>
    </div>
  </div>

  <div class="user-info flex">
    <img src="./images/avatar.png" alt="">
    <div>
      <div class="name flex">
        <span>高先生</span>
        <span>感兴趣</span>
      </div>
      <div>
        京东集团·招聘者
      </div>
    </div>
    <button class="btn">立即沟通</button>
  </div>

  <div class="job-detail">
    <h3>职位描述</h3>
    <div class="text">
      岗位职责：<br>1.本科及以上学历<br>2.精通HTML、JavaScript、Ajax、CSS等Web开发技术
      <br>3.具有审美和设计能力，注重细节，追求完美,会简单使用photoshop等工具<br>4.能熟练使用主流的JavaScript框架或JavaScript库,熟练运用react/angular/vue中的一种
      <br>5.能使用grunt/gulp/webpack进行环境构建，了解velocity、jsp、freemarker中的一种
      <br>6.熟悉echarts、highcharts优先考虑<br>7.实现产品前端ui和交互方面的开发需求，确保不同平台、设备上具有优秀的用户体验；<br>8.对Web标准和兼容性有良好认识，能够高保真还原设计稿，具备良好的代码风格以及接口、架构设计能力<br>9.有良好的沟通能力和团队合作能力，善于沟通，工作自主驱动，具备良好的问题定位分析能力
    </div>

    <h3>团队介绍</h3>
    <div class="tags">
      <span>不打卡</span>
      <span>公司氛围好</span>
      <span>领导nice</span>
    </div>

    <h3>公司介绍</h3>
    <div class="text">
      京东于2004年正式涉足电商领域。2016年，京东集团市场交易额达到9392亿元*。京东是中国收入规模最大的互联网企业。2017年7月，京东再次入榜《财富》全球500强，位列第261位，成为排名最高的中国互联网企业，在全球仅次于亚马逊和Alphabet，位列互联网企业第三。2018年财富世界500强
    </div>

    <h3>工商信息</h3>
    <div class="text">
      北京京东世纪贸易有限公司
      <table>
        <tr>
          <td>法人代表：</td>
          <td>刘强东</td>
          <td>注册资本</td>
          <td>139798.5564万美元</td>
          <td>成立时间</td>
          <td>2007.04-20</td>
          <td>经营状态</td>
          <td>开业</td>
        </tr>
      </table>
      <div><small>数据来源：企查查</small></div>
    </div>

    <h3>工作地址</h3>
    <div class="map">

    </div>

    <div class="company-info flex">
      <img src="./images/company-logo.jpg" alt="">
      <div class="">
        <div class="name">
          <span>京东集团</span>
          <div class="btn" type="button">关注该公司</div>
        </div>
        <div>北京京东世纪贸易有限公司</div>
        <div class="tags">
          电子商务 <i></i>
          已上市 <i></i>
          10000人以上
        </div>
      </div>
    </div>

    <div class="related-jobs">
      <h3>相似职位</h3>
      <li>
        <a href="" class="job-item flex">
          <img src="./images/company-logo.jpg" alt="">
          <div class="text">
            <div class="title flex">
              web前端
              <span class="salary">11-17K·13薪</span>
            </div>
            <div class="flex">
                <div class="company">
                    京东集团
                  </div>
                <button type="button">立即沟通</button>  
            </div>
          </div>
        </a>
      </li>
    </div>
  </div>

  <div class="related-companies">
    <h3>推荐公司：</h3>
    <div class="tags">
      <a href="">文思海辉·金融</a>
      <a href="">健客网</a>
      <a href="">VIPKID</a>
      <a href="">滴滴</a>
    </div>
  </div>

  <div class="job-footer breadcrumb-nav">
    <a href="">首页</a> <i></i>
    <a href="">北京Web前端招聘</a> <i></i>
    <a href="">北京Web</a> <i></i>
    <a href="">Web前端</a> <i></i>
  </div>
</body>

</html>
```

