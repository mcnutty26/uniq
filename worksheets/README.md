# Worksheet 2 Snippet
Because no one has time to type out that function from worksheet 2:
```R
image_prep = function(x) {
    arrays = lapply(x, function(path) {
        img = image_load(path, target_size = c(224,224))
        x = image_to_array(img)
        x = array_reshape(x, c(1, dim(x)))
        x = imagenet_preprocess_input(x)
    })
    do.call(abind::abind, c(arrays, list(along = 1)))
}
```
