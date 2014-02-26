# bloggy-query

> A set of fluent methods to query posts and tags of blog entries of bloggy, a small and lightweight blog engine for node.js.

## Quickstart

That's everything you need. Just call the `engine.extendWith()` function of the bloggy engine.

```Javascript
var engine = require('bloggy')();

engine.extendWith(require('bloggy-query'));
```

## Methods

After registering the engine contains these additional functions.


**Get all blog entries (ordered by name)**

```Javascript
var entries = engine.entries.all.orderedByName();
```

**Get all blog entries (ordered by date [descending])**

```Javascript
var entries = engine.entries.all.orderedByDate();
```

**Get entries containing a specific tag slug**

```Javascript
var entries = engine.entries.byTagSlug('Continuous-Integration');
```

**Get one entry by its slug**

```Javascript
var entry = engine.entry.bySlug('How-to-deploy-to-Travis-CI');
```

**Get one entry by its short title**

```Javascript
var entry = engine.entry.byShortTitle('travisdeploy');
```

**Get the latest/newest entry**

```Javascript
var entry = engine.entry.latest();
```

**Get all tags (ordered by the number of usages)**

```Javascript
var tags = engine.tags.all();

[
    { count: 5, tag: { name: 'tech', slug: 'tech'} },
    { count: 4, tag: { name: 'nodejs', slug: 'nodejs'} },
    { count: 1, tag: { name: 'Continuous Integration', slug: 'Continuous-Integration'} },
]
```

**Get all tags names**

```Javascript
var tagNames = engine.tags.asNames();

['tech', 'nodejs', 'Continuous Integration']
```

License
-------

The MIT License (MIT)

Copyright (c) 2014 Marcell Spies

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.