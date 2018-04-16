---
title: 4. Secondary Indexes
linkTitle: 4. Secondary Indexes
description: Secondary Indexes
aliases:
  - /explore/secondary-indexes/
menu:
  latest:
    identifier: secondary-indexes
    parent: explore
    weight: 231
---

A database index is a data structure that improves the speed of data retrieval operations on a database table. Secondary indexes require additional writes and storage space to maintain the index data structure. They can be created using one or more columns of a database table, providing the basis for both rapid random lookups and efficient access of ordered records.

YugaByte DB provides consistent (ACID), performant secondary indexes. They are built on top of [distributed ACID transactions](../transactions.md). You can [read more about transactions](../../architecture/transactions/) in our architecture docs.

If you haven't installed YugaByte DB yet, do so first by following the [Quick Start](../../quick-start/install/) guide.

**NOTE:** Secondary indexes are a work in progress. Here are some requirements to keep in mind currently when using secondary indexes in YugaByte:

- To create a secondary index on a table, the primary table needs to be created with distributed transaction enabled using the `with transactions = { 'enabled' : true }` clause.
- The secondary index needs to be created before any data is inserted into the primary table.
- A secondary index will be used to execute a query only when the index covers all columns selected by the query.

These requirements may be removed in the future.

<ul class="nav nav-tabs nav-tabs-yb">
  <li class="active">
    <a href="#docker">
      <i class="icon-docker"></i>
      Docker
    </a>
  </li>
  <li>
    <a href="#kubernetes">
      <i class="fa fa-cubes" aria-hidden="true"></i>
      Kubernetes
    </a>
  </li>
  <li >
    <a href="#macos">
      <i class="fa fa-apple" aria-hidden="true"></i>
      macOS
    </a>
  </li>
  <li>
    <a href="#linux">
      <i class="fa fa-linux" aria-hidden="true"></i>
      Linux
    </a>
  </li>
</ul>

<div class="tab-content">
  <div id="docker" class="tab-pane fade in active">
    {{% includeMarkdown "docker/secondary-indexes.md" /%}}
  </div>
  <div id="kubernetes" class="tab-pane fade">
    {{% includeMarkdown "kubernetes/secondary-indexes.md" /%}}
  </div>
  <div id="macos" class="tab-pane fade">
    {{% includeMarkdown "binary/secondary-indexes.md" /%}}
  </div>
  <div id="linux" class="tab-pane fade">
    {{% includeMarkdown "binary/secondary-indexes.md" /%}}
  </div> 
</div>