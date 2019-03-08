# Responsive coding practice

#What I learned:

### Blur background image

`html`
```
<div class="background_image">
Content
</div>
```

`css`
```
.background_image {
    background: url(../images/top.jpg) no-repeat center center;
    background-size: cover;
    z-index:0;
    position: relative;
    overflow: hidden; 
}
.background_image::before {
    filter: blur(4px);
    background: inherit;
    content: '';
    position: absolute;
    z-index: -1;
    top: -4px;
    bottom: -4px;
    left: -4px;
    right: -4px;
}
```

## Align SVG with background with transform property

`html`
```
<div class="icon">
    <svg role="img">
            <use xlink:href="sprite.svg"></use>
    </svg>                                
</div>
```

`css`
```
.icon {
    position: relative;
    width: 60px;
    height: 60px;
    border-radius: 50%;
}

svg {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    fill: #fff;
}
```

## Align SVG with background using Flex


## Generate SVG sprite using npm svg-sprite

Directory structure:  
/project  
├ /assets  
│ └ /svg // *SVG sprite  
├ /svg  // *svg files  
└ index.html  

### 1. Install svg-sprite  
npm install svg-sprite    

### 2. Create config.json file  


### 3. Run command  
svg-sprite -C config.json --shape-transform-svgo svgo.json svg/*.svg  

### 4. Display on html  
`Example`
```
<svg class="logo" role="img">
  <use xlink:href="/assets/svg/sprite.svg#nameOfSVGfile"></use>
</svg>
```