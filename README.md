

# پیاده‌سازی گراف در جاوااسکریپت

این یک پیاده‌سازی ساده از یک گراف جهت‌دار در جاوااسکریپت است. یک گراف شامل مجموعه‌ای از گره‌ها (نودها) و یال‌ها (لبه‌ها) است که به ترتیب نمایش داده می‌شوند.

## استفاده

ابتدا یک نمونه جدید از `Graph` ایجاد کنید:

```javascript
const graph = new Graph();
```

### `addNode(id, value)`

یک گره جدید با شناسه (id) و مقدار (value) داده شده به گراف اضافه می‌کند.

```javascript
graph.addNode(1, 'A');
graph.addNode(2, 'B');
graph.addNode(3, 'C');
```

### `addEdge(startNode, endNode)`

یک یال جدید از `startNode` به `endNode` اضافه می‌کند.

```javascript
graph.addEdge(1, 2);
graph.addEdge(2, 3);
graph.addEdge(1, 3);
```

### `removeNode(nodeId)`

گره با شناسه داده شده `nodeId` را از گراف حذف می‌کند و همچنین تمامی یال‌های مربوط به آن گره را پاک می‌کند.

```javascript
graph.removeNode(2);
```

## مثال

```javascript
const graph = new Graph();

graph.addNode(1, 'A');
graph.addNode(2, 'B');
graph.addNode(3, 'C');

graph.addEdge(1, 2);
graph.addEdge(2, 3);
graph.addEdge(1, 3);

console.log(graph.node); // خروجی: { '1': 'A', '2': 'B', '3': 'C' }
console.log(graph.edge); // خروجی: { '1': [ 2, 3 ], '2': [ 3 ] }

graph.removeNode(2);

console.log(graph.node); // خروجی: { '1': 'A', '2': undefined, '3': 'C' }
console.log(graph.edge); // خروجی: { '1': [ 3 ] }
```

## نکات

- اگر گره‌ای که می‌خواهید اضافه کنید از قبل وجود داشته باشد، مقدار آن به روز رسانی می‌شود.
- اگر یالی که می‌خواهید اضافه کنید از قبل وجود داشته باشد، تکراری ایجاد نمی‌شود.
- هنگام حذف گره، تمام یال‌های ورودی و خروجی مربوط به آن گره نیز حذف می‌شوند.


