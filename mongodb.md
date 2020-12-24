### <text style="color:red;">GROUPBY 操作</text>
mongodb 聚合:
```管道
{
    _id: "$type",
    items: {
        $push: {
            name: "$name",
            url: "$url",
            coverage: "$coverage",
            singer: "$singer"
        }
    },
    count: {
        $sum: 1
    }
}
```
unicloud中使用方法:
```
db.collection('music').aggregate().group({
		_id: "$type",
		items: {
			$push: {
				name: "$name",
				url: "$url",
				coverage: "$coverage",
				singer: "$singer"
			}
		},
		count: {
			$sum: 1
		}
	}).end()
```
