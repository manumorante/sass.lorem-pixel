# Pixer - Lorem Pixel sass-mixin

Manu Morante #17/02/2015 | More info about image service: http://lorempixel.com/

## Usage

*Fixed dimensions (400x350), random category and random id.*
```scss
background: pixer(); 
```
*Specific id, fixed dimension (400x350) and category nature.*
```scss
background: pixer(1);
```
*Specific dimensions, random category and random id.*
```scss
background: pixer(800, 600);
```
*Specific dimensions and category. Ramdom Id.*
```scss
background: pixer(800, 600, people);
```
*Specific*
```scss
background: pixer(800, 600, people, 1);
```
*Without 'url()'*
```scss
background: image-url("#{ pixer(800, 600, $out-url: false) }");
```
 
## Return
```scss
background: url("//lorempixel.com/400/350/");
background: url("//lorempixel.com/800/600/");
background: url("//lorempixel.com/400/350/nature/1");
background: url("//lorempixel.com/800/600/people/");
background: url("//lorempixel.com/800/600/people/1/");
background: image-url("//lorempixel.com/800/600/people/1/");
```
