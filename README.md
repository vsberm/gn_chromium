
## 1. install

1. create `.gclient` file
2. gclient sync
3. gclient runhooks
```
solutions = [
  {
    "url": "https://github.com/vsberm/gn_example.git",
    "managed": False,
    "name": "src",
    "deps_file": "DEPS",
    "custom_deps": {},
  },
]

```

## 2. build

Debug:
```
gn gen --ide=vs out\Default
ninja -C out\Default
```

Release:
```
gn gen --ide=vs out\Release --args="is_debug=false is_component_build=false"
ninja -C out\Release
```

Or:
```
ninja -C out\debug gn_example
```