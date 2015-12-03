# Lorem Pixel SASS mixin

Manu Morante #17/02/2015 | More info about image service: http://lorempixel.com/

## Usage

Fixed dimension. Random category and id
```scss
background: lorem-pixel-url(); 
```
Fixed dimension. 'Nature' category and specific id
```scss
background: lorem-pixel-url(1);
```
Random category and id
```scss
background: lorem-pixel-url(800, 600);
```
Ramdom Id in a category
```scss
background: lorem-pixel-url(800, 600, people);
```
Specific
```scss
background: lorem-pixel-url(800, 600, people, 1);
```
Without 'url()'
```scss
background: url("#{ lorem-pixel-url(800, 600, $out-url: false) }");
```
 
## Return
```scss
background: url("//lorempixel.com/400/350/");
background: url("//lorempixel.com/800/600/");
background: url("//lorempixel.com/400/350/nature/1");
background: url("//lorempixel.com/800/600/people/");
background: url("//lorempixel.com/800/600/people/1/");
background: url("//lorempixel.com/800/600/people/1/");
```

```scss
@import "compass/css3";

@function lorem-pixel-url($width: 400, $height: 350, $category: false, $num: false, $out-url: true){
  $url: "//lorempixel.com/#{$width}/#{$height}/";
  
  // Using width as number of photo
  @if $width <= 10 {
    $url: "//lorempixel.com/400/350/nature/"+ $width +"/";
    
  } @else {
    @if $category {
      $url: $url + $category +'/';
      @if $num { $url: $url + $num +'/'; }
    }
  } 
  
  @if $out-url { $url: url($url) }
  @return $url;
}
```
