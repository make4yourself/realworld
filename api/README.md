# RealWorld API 规格

## 本地执行 API tests

若要对后端执行对本地运行提供的 Postman collection ，请执行：

```
APIURL=http://localhost:3000/api ./run-api-tests.sh
```

更多详情请见 [`run-api-tests.sh`](run-api-tests.sh).

## 在后端使用 [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) 需要注意的事项

如果后端是运行在与前端不同的主机/端口上，请确保也处理了`OPTINS` 并且返回正确的 `Access-Control-Allow-Origin` 和 `Access-Control-Allow-Headers` (例如, `Content-Type`)

### Authentication Header:

`Authorization: Token jwt.token.here`

## API 返回的 JSON 对象:

确保正确的内容类型如 `Content-Type: application/json; charset=utf-8` 被正确的返回。

### 用户（Users (for authentication)）

```JSON
{
  "user": {
    "email": "jake@jake.jake",
    "token": "jwt.token.here",
    "username": "jake",
    "bio": "I work at statefarm",
    "image": null
  }
}
```

### 用户简况（Profile）

```JSON
{
  "profile": {
    "username": "jake",
    "bio": "I work at statefarm",
    "image": "https://static.productionready.io/images/smiley-cyrus.jpg",
    "following": false
  }
}
```

### 单个文章（Single Article）

```JSON
{
  "article": {
    "slug": "how-to-train-your-dragon",
    "title": "How to train your dragon",
    "description": "Ever wonder how?",
    "body": "It takes a Jacobian",
    "tagList": ["dragons", "training"],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "favorited": false,
    "favoritesCount": 0,
    "author": {
      "username": "jake",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "following": false
    }
  }
}
```

### 多个文章（Multiple Articles）

```JSON
{
  "articles":[{
    "slug": "how-to-train-your-dragon",
    "title": "How to train your dragon",
    "description": "Ever wonder how?",
    "body": "It takes a Jacobian",
    "tagList": ["dragons", "training"],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "favorited": false,
    "favoritesCount": 0,
    "author": {
      "username": "jake",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "following": false
    }
  }, {
    "slug": "how-to-train-your-dragon-2",
    "title": "How to train your dragon 2",
    "description": "So toothless",
    "body": "It a dragon",
    "tagList": ["dragons", "training"],
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:48:35.824Z",
    "favorited": false,
    "favoritesCount": 0,
    "author": {
      "username": "jake",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "following": false
    }
  }],
  "articlesCount": 2
}
```

### 单条评论（Single Comment）

```JSON
{
  "comment": {
    "id": 1,
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:22:56.637Z",
    "body": "It takes a Jacobian",
    "author": {
      "username": "jake",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "following": false
    }
  }
}
```

### 多条评论（Multiple Comments）

```JSON
{
  "comments": [{
    "id": 1,
    "createdAt": "2016-02-18T03:22:56.637Z",
    "updatedAt": "2016-02-18T03:22:56.637Z",
    "body": "It takes a Jacobian",
    "author": {
      "username": "jake",
      "bio": "I work at statefarm",
      "image": "https://i.stack.imgur.com/xHWG8.jpg",
      "following": false
    }
  }]
}
```

### 标签列表（List of Tags）

```JSON
{
  "tags": [
    "reactjs",
    "angularjs"
  ]
}
```

### 错误和错误状态码（Errors and Status Codes）

如果一个请求没有通过任何的验证，那么就会出现 422 并且会有以下格式的错误信息：

```JSON
{
  "errors":{
    "body": [
      "can't be empty"
    ]
  }
}
```

#### 其他的状态码:

401 表示未经授权的请求，当一个请求需要认证，但没有提供认证信息

403 表示被禁止的请求，当请求可能是有效的，但是用户没有执行该操作权限

404 表示未找到的请求，当无法找到满足请求的资源时


## 端点：

### 认证：

`POST /api/users/login`

请求体样例：

```JSON
{
  "user":{
    "email": "jake@jake.jake",
    "password": "jakejake"
  }
}
```

不需要认证，返回一个 [用户](#用户（Users (for authentication)）)

必须包含请求字段： `email`, `password`


### 注册：

`POST /api/users`

请求体样例：
```JSON
{
  "user":{
    "username": "Jacob",
    "email": "jake@jake.jake",
    "password": "jakejake"
  }
}
```

不需要认证，返回一个 [用户](#用户（Users (for authentication)）)

必须包含请求字段：`email`, `username`, `password`



### 登录用户信息

`GET /api/user`

认证必须，返回当前 [用户](#用户（Users (for authentication)）) 信息



### 更新用户信息

`PUT /api/user`

请求体样例：
```JSON
{
  "user":{
    "email": "jake@jake.jake",
    "bio": "I like to skateboard",
    "image": "https://i.stack.imgur.com/xHWG8.jpg"
  }
}
```

认证必须，返回 [用户](#用户（Users(for-authentication)）) 信息


必须包含请求字段：`email`, `username`, `password`, `image`, `bio`



### 获取用户信息

`GET /api/profiles/:username`

可选认证，返回 [用户简况](#用户简况（Profile）)



### 关注用户

`POST /api/profiles/:username/follow`

认证必须，返回 [用户简况](#用户简况（Profile）)

不需要其他参数



### 取消用户关注

`DELETE /api/profiles/:username/follow`

认证必须，返回 [用户简况](#用户简况（Profile）)

不需要其他参数



### 文章列表

`GET /api/articles`

全局默认返回最近的文章，提供 `tag`， `author` 或者是 `favorited` 查询参数来过滤结果 

请求参数：

通过 `tag` 过滤

`?tag=AngularJS`

通过 `author` 过滤

`?author=jake`

被某个用户喜欢

`?favorited=jake`

限制文章数量 （默认值 20）：

`?limit=20`

偏移/跳过文章数量 （默认值 0）：

`?offset=0`

可选认证， 会返回最近的 [多个文章](多个文章（Multiple Articles）)



### 抓取文章

`GET /api/articles/feed`

同样可以使用 `limit` 和 `offset`请求参数像 [文章列表](#文章列表)

认证必须， 将会返回多个用户所关注的用户最近发布的[多篇文章](#多个文章（Multiple Articles）)


### 文章详细

`GET /api/articles/:slug`

非认证必须， 将会返回 [单个文章](#单个文章（Single Article）)

### 创建文章

`POST /api/articles`

请求体样例：

```JSON
{
  "article": {
    "title": "How to train your dragon",
    "description": "Ever wonder how?",
    "body": "You have to believe",
    "tagList": ["reactjs", "angularjs", "dragons"]
  }
}
```

认证必须， will return an [Article](#single-article)

必须包含请求字段： `title`, `description`, `body`

可选包含请求字段：`tagList` as an array of Strings



### 更新文章

`PUT /api/articles/:slug`

请求体样例：

```JSON
{
  "article": {
    "title": "Did you train your dragon?"
  }
}
```

认证必须， 返回更新后的 [文章](#单个文章（Single Article）)

可选包含请求字段：`title`, `description`, `body`

 `slug` 字段同样也会在 `title` 字段被更新后更新


### 删除文章

`DELETE /api/articles/:slug`

认证必须



### 对一篇文章评论

`POST /api/articles/:slug/comments`

请求体样例：

```JSON
{
  "comment": {
    "body": "His name was my name too."
  }
}
```

认证必须， 返回创建好的 [评论](#单条评论（Single Comment）)

必须包含请求字段： `body`



### 获取文章小的所有评论

`GET /api/articles/:slug/comments`

可选认证，返回 [多条评论](#多条评论（Multiple Comments）)



### 删除评论

`DELETE /api/articles/:slug/comments/:id`

认证必须



### 喜欢一篇文章

`POST /api/articles/:slug/favorite`

认证必须， 返回 [文章](#单个文章（Single Article）)

不需要其他参数



### 取消喜欢一盘文章

`DELETE /api/articles/:slug/favorite`

认证必须， 返回 [文章](#单个文章（Single Article）)#single-article)

不需要其他参数



### 获取标签

`GET /api/tags`

非认证必须，返回 [标签列表](#标签列表（List of Tags）)
