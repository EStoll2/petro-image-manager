# petro-image-manager
Convert images from TIF to DZI format for use in https://github.com/grsharman/petro-image

### Image conversion

1. Install VIPS (or similar tool)
2. Copy `.tif` files into the folder ./tif-images/
3. Use the command line to convert images from `.tif` to `.dzi`:

```
convert-tif () {
    i="${1##./tif-images/}";
    image_name="${i%%.tif}";
    vips dzsave "${1}" "./dzi-images/${image_name}";
};

for image in $(ls ./tif-images/*.tif)
do
    convert-tif "$image";
done
```

4. Find the output images in ./dzi-images/
