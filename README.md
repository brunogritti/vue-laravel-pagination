## Vue pagination for Laravel

> A Laravel Paginator for vue3 components

# Installation

### Obs

To Vue2, use branch ```main```\
To Vue2, use branch ```vue3```

## npm

```

npm install vue3-laravel-custom-pagination

```


## Then

```$xslt

import Pagination from 'vue3-laravel-custom-pagination'

```

**Then that's how you insert in the .vue template:**

```$xslt

<template>

    ...

    <pagination
        ref="pagination"
        :from="results.from"
        :to="results.to"
        :total="results.total"
        @page-changed="fetch"></pagination>

</template>

```

> The 'page-changed' event is emmitted when the next or previous button is clicked.
> There are properties inside the component data called page and limit, you can use them in your component by giving <paginator> a ref and then calling the values like `this.$refs.pagination.page`.


## Roadmap

* Make CSS customizable
* Make props for diferent layouts (simple buttons, show page number, show total results, etc)


## License

This Laravel package is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)