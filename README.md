# Vue Image Annotations

This is an example Vue component that wraps the [Annotorious](https://annotorious.github.io/index.html) javascript library. 
The AnnotatedImage component can easily connected to a backend service for retrieving and storing annotations as follows:

- in the `init()` method you can invoke a backend service to retrieve the initial set of annotations. An example for initializing
    annotations is given.
    
- the `onAnnotationCreated()`, `onAnnotationUpdated()`, and `onAnnotationDeleted()` methods can invoke a backend service.


## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
