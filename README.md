# Демонстрационное API для поиска информации по городам
Сделано с использованием [json-server](https://github.com/typicode/json-server).

## Роуты
* [/cities-russia](https://cities-web-api.herokuapp.com/cities-russia?q=новосибирск&_limit=10)
* [/cities-with-population](https://cities-web-api.herokuapp.com/cities-with-population?q=novosibirsk&_limit=10)
* [/cities-world](https://cities-web-api.herokuapp.com/cities-world?q=novosibirsk&_limit=10)
* [/towns-russia](https://cities-web-api.herokuapp.com/towns-russia?q=новосибирск&_limit=10)

## Формат запроса (взято [отсюда](https://github.com/typicode/json-server#paginate))
### Filter

Use `.` to access deep properties

```
GET /posts?title=json-server&author=typicode
GET /posts?id=1&id=2
GET /comments?author.name=typicode
```

### Paginate

Use `_page` and optionally `_limit` to paginate returned data.

In the `Link` header you'll get `first`, `prev`, `next` and `last` links.


```
GET /posts?_page=7
GET /posts?_page=7&_limit=20
```

_10 items are returned by default_

### Sort

Add `_sort` and `_order` (ascending order by default)

```
GET /posts?_sort=views&_order=asc
GET /posts/1/comments?_sort=votes&_order=asc
```

For multiple fields, use the following format:

```
GET /posts?_sort=user,views&_order=desc,asc
```

### Slice

Add `_start` and `_end` or `_limit` (an `X-Total-Count` header is included in the response)

```
GET /posts?_start=20&_end=30
GET /posts/1/comments?_start=20&_end=30
GET /posts/1/comments?_start=20&_limit=10
```

_Works exactly as [Array.slice](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) (i.e. `_start` is inclusive and `_end` exclusive)_

### Full-text search

Add `q`

```
GET /posts?q=internet
```

