# PaperFigure

## Run

You need to launch a server at first.
```sh
cd $YOUR_DIR/PaperFigure
python -m http.server 8000
```

Then, copy `http://0.0.0.0:8000/` into your browser. Now, you can take screenshot of the images for your paper.

## Customizing the style

### Change the color and size of the image zoom lens

The style of the image zoom lens is defined at `magnifier.css`:

```css
.img-zoom-lens {
    position: absolute;
    border: 3px;
    border-color:yellow;
    
    width: 80px;
    height: 80px;
}
```

### Change the number of images 

For the image zoom-in effect, you can adapt it to any number of images you want to show in your paper. For example, 
if you have 6 scenes in your NeRF dataset, you can name them by `000.png`, `001.png`, ..., `005.png`. Then, create folders for different methods, e.g. one for ground truth `gt`, one for method1 `m1`, one for method2 `m2`, and the last is your method `ours`. You can now put all the images obtained by different methods under the corresponding folder. At last, you need to modify the image number in `index.html` at Line-368:
```javascript
<script>
    num_images = 2; // Modify this to the number of your images.
    imageZoom("ground_truth", ["zoomed-barf_rgb", "zoomed-ibrnet_rgb", "zoomed-dbarf_rgb" ], num_images); 
</script>
```
