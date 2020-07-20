# border1px scss version

mobile border1px scss version

this scss file is used for fix mobile 1px border in retina screen problem

it can be easy to understand and use

## Usage

You should add what you created class into your html tag

eg:You created class name as `border-btn`

### in html

``` html
...
<div class="other-class border-btn"></div>
...

```

####  border:1px dashed #979797

```css
// usage.scss
@import "@/scss/border1px.scss";

@include borderCreator("btn", "", dashed, #979797); //create class named `border-btn`
```

result in css

```css
.border-btn {
    border: 1px dashed #979797;
}

@media screen and (-webkit-min-device-pixel-ratio: 2){
	.border-btn {
	    border: 0.5px dashed #979797;
	}
}

@media screen and (-webkit-min-device-pixel-ratio: 3){
	.border-btn {
	    border: 0.333333px dashed #979797;
	}
}

```


#### border-bottom:1px solid rgba(185, 185, 185, 0.5)

```css
// usage.scss
@import "@/scss/border_1px.scss";

@include borderCreator("cut-line", "bottom", solid, rgba(185, 185, 185, 0.5));
```

result in css

```css
.border-cut-line {
    border-bottom: 1px solid rgba(185, 185, 185, 0.5);
}

@media screen and (-webkit-min-device-pixel-ratio: 2){
	.border-cut-line {
    	border-bottom: 0.5px solid rgba(185, 185, 185, 0.5);
	}
}

@media screen and (-webkit-min-device-pixel-ratio: 3){
	.border-cut-line {
	    border-bottom: 0.333333px solid rgba(185, 185, 185, 0.5);
	}
}
```

### use for including a Mixin to a class
``` scss
 @import "@/scss/border1px.scss";

 .content{
    @include  borderInsideCreator("top","solid","#000")
    color:red;
 }
 
 //will be
 
 .content{
    color:red;
    border-top: 1px solid #000;
    @media screen and (-webkit-min-device-pixel-ratio: 2) {
      border-top: 0.5px solid #000;
    }
    @media screen and (-webkit-min-device-pixel-ratio: 3) {
      border-top: 0.333333px solid #000;
    }
  }
```

