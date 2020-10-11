# MongoDB CRUD Operations MongoDB中的CURD操作

> On this page 本页面中
>
> - [Create Operations 创建操作](https://docs.mongodb.com/manual/crud/#create-operations)
> - [Read Operations 读操作](https://docs.mongodb.com/manual/crud/#read-operations)
> - [Update Operations 更新操作](https://docs.mongodb.com/manual/crud/#update-operations)
> - [Delete Operations 删除操作](https://docs.mongodb.com/manual/crud/#delete-operations)
> - [Bulk Write 批量写](https://docs.mongodb.com/manual/crud/#bulk-write)

CRUD operations *create*, *read*, *update*, and *delete* [documents](https://docs.mongodb.com/manual/core/document/#bson-document-format).<br>CURD操作指的是文档的*创建*、*读*、*更新*以及*删除*操作。

## Create Operations 创建操作

Create or insert operations add new [documents](https://docs.mongodb.com/manual/core/document/#bson-document-format) to a [collection](https://docs.mongodb.com/manual/core/databases-and-collections/#collections). If the collection does not currently exist, insert operations will create the collection.<br>创建或者插入操作将新的文档添加到一个集合中。如果集合当前并不存在，插入操作会创建该集合。

MongoDB provides the following methods to insert documents into a collection:<br>MongoDB提供了以下两个方法来向集合中插入文档：

- [`db.collection.insertOne()`](https://docs.mongodb.com/manual/reference/method/db.collection.insertOne/#db.collection.insertOne) *New in version 3.2* *3.2版本引入*
- [`db.collection.insertMany()`](https://docs.mongodb.com/manual/reference/method/db.collection.insertMany/#db.collection.insertMany) *New in version 3.2* *3.2版本引入*

In MongoDB, insert operations target a single [collection](https://docs.mongodb.com/manual/reference/glossary/#term-collection). All write operations in MongoDB are [atomic](https://docs.mongodb.com/manual/core/write-operations-atomicity/) on the level of a single [document](https://docs.mongodb.com/manual/core/document/).<br>在MongoDB中，插入操作只针对单个集合。MongoDB中的所有写操作都是单个文档级别的原子操作。

![The components of a MongoDB insertOne operations.](https://docs.mongodb.com/manual/_images/crud-annotated-mongodb-insertOne.bakedsvg.svg)

For examples, see [Insert Documents](https://docs.mongodb.com/manual/tutorial/insert-documents/).<br>关于示例，请参考【插入文档】。

## Read Operations 读操作

Read operations retrieves [documents](https://docs.mongodb.com/manual/core/document/#bson-document-format) from a [collection](https://docs.mongodb.com/manual/core/databases-and-collections/#collections); i.e. queries a collection for documents. MongoDB provides the following methods to read documents from a collection:<br>读操作从一个集合中检索文档；即查询集合中的文档。MongoDB提供了以下方法来从集合中读取文档：

- [`db.collection.find()`](https://docs.mongodb.com/manual/reference/method/db.collection.find/#db.collection.find)

You can specify [query filters or criteria](https://docs.mongodb.com/manual/tutorial/query-documents/#read-operations-query-argument) that identify the documents to return.<br>你可以指定查询过滤器或条件来标识要返回的文档

![The components of a MongoDB find operation.](https://docs.mongodb.com/manual/_images/crud-annotated-mongodb-find.bakedsvg.svg)

For examples, see:<br>更多示例，请参考：

- [Query Documents 查询文档](https://docs.mongodb.com/manual/tutorial/query-documents/)
- [Query on Embedded/Nested Documents 查询嵌入式文档](https://docs.mongodb.com/manual/tutorial/query-embedded-documents/)
- [Query an Array 查询数据](https://docs.mongodb.com/manual/tutorial/query-arrays/)
- [Query an Array of Embedded Documents 查询嵌入式文档的数组](https://docs.mongodb.com/manual/tutorial/query-array-of-documents/)

## Update Operations 更新操作

Update operations modify existing [documents](https://docs.mongodb.com/manual/core/document/#bson-document-format) in a [collection](https://docs.mongodb.com/manual/core/databases-and-collections/#collections). MongoDB provides the following methods to update documents of a collection:<br>更新操作修改一个集合中已存在的文档。MongoDB提供了以下方法来更新一个集合中的文档：

- [`db.collection.updateOne()`](https://docs.mongodb.com/manual/reference/method/db.collection.updateOne/#db.collection.updateOne) *New in version 3.2* *3.2版本引入*
- [`db.collection.updateMany()`](https://docs.mongodb.com/manual/reference/method/db.collection.updateMany/#db.collection.updateMany) *New in version 3.2* *3.2版本引入*
- [`db.collection.replaceOne()`](https://docs.mongodb.com/manual/reference/method/db.collection.replaceOne/#db.collection.replaceOne) *New in version 3.2* *3.2版本引入*

In MongoDB, update operations target a single collection. All write operations in MongoDB are [atomic](https://docs.mongodb.com/manual/core/write-operations-atomicity/) on the level of a single document.<br>在MongoDB中，更新操作只针对单个集合。MongoDB中的所有写操作都是单个文档级别的原子操作。

You can specify criteria, or filters, that identify the documents to update. These [filters](https://docs.mongodb.com/manual/core/document/#document-query-filter) use the same syntax as read operations.<br>你可以指定查询过滤器或条件来标识要更新的文档，这里的过滤器和读操作的语法是一致的。

![The components of a MongoDB updateMany operation.](https://docs.mongodb.com/manual/_images/crud-annotated-mongodb-updateMany.bakedsvg.svg)

For examples, see [Update Documents](https://docs.mongodb.com/manual/tutorial/update-documents/).<br>关于示例，请参考【更新文档】。

## Delete Operations 删除操作

Delete operations remove documents from a collection. MongoDB provides the following methods to delete documents of a collection:<br>删除操作从一个集合中删除文档。MongoDB提供了以下方法来从一个集合中删除文档：

- [`db.collection.deleteOne()`](https://docs.mongodb.com/manual/reference/method/db.collection.deleteOne/#db.collection.deleteOne) *New in version 3.2* *3.2版本引入*
- [`db.collection.deleteMany()`](https://docs.mongodb.com/manual/reference/method/db.collection.deleteMany/#db.collection.deleteMany) *New in version 3.2* *3.2版本引入*

In MongoDB, delete operations target a single [collection](https://docs.mongodb.com/manual/reference/glossary/#term-collection). All write operations in MongoDB are [atomic](https://docs.mongodb.com/manual/core/write-operations-atomicity/) on the level of a single document.<br>在MongoDB中，删除操作只针对单个集合。MongoDB中的所有写操作都是单个文档级别的原子操作。

You can specify criteria, or filters, that identify the documents to remove. These [filters](https://docs.mongodb.com/manual/core/document/#document-query-filter) use the same syntax as read operations.<br>你可以指定查询过滤器或条件来标识要更新的文档，这里的过滤器和读操作的语法是一致的。

![The components of a MongoDB deleteMany operation.](https://docs.mongodb.com/manual/_images/crud-annotated-mongodb-deleteMany.bakedsvg.svg)

For examples, see [Delete Documents](https://docs.mongodb.com/manual/tutorial/remove-documents/).<br>关于示例，请参考【删除文档】。

## Bulk Write 批量写

MongoDB provides the ability to perform write operations in bulk. For details, see [Bulk Write Operations](https://docs.mongodb.com/manual/core/bulk-write-operations/).<br>MongoDB提供了批量执行写操作的能力。更多细节请参考【批量写操作】。



原文链接：https://docs.mongodb.com/v4.2/crud/

译者：刘翔
