# Cross Rhythm

Cross Rhythm provides some mixins which override [Compass Vertical Rhythm](http://compass-style.org/reference/compass/typography/vertical_rhythm/) and allow you to layout both horizontal and vertical writing documents.

Cross Rhythm overrides the following mixins:

* leader
* padding-leader
* margin-leader
* trailer
* padding-trailer
* margin-trailer
* rhythm
* leading-border
* trailing-border
* horizontal-borders
* h-borders

## How to use

Import Cross Rhythm in stead of Vertical Rhythm.

For horizontal writing document:

```scss
@import "cross_rhythm";
```

For vertical writing document:

```scss
@import "cross_rhythm";
$vertical-writing: true;
```

## Examples

```scss
.foo {
	@include leader();
}
```

the result is same as the original Vertical Rhythm.

```css
.foo {
  margin-top: 1.5em;
}
```

But if `$vertical-writing` is `true`,

```scss
$vertical-writing: true;

.foo {
	@include leader();
}
```

you got

```css
.foo {
  margin-right: 1.5em;
}
```

If you want to specify vertical writing partially, set `true` to the 4th extra argument.

```scss
.foo {
	@include leader(1, $base-font-size, margin);
}
 
.bar {
	@include leader(1, $base-font-size, margin, true);
}
```

then you got

```css
.foo {
  margin-top: 1.5em;
}

.bar {
  margin-right: 1.5em;
}
```

## Mixin

Set `true` to `$is-vert` for vertical writing.

```
leader($lines, $font-size, $property, $is-vert: $vertical-writing)
```

```
padding-leader($lines, $font-size, $is-vert: $vertical-writing)
```

```
margin-leader($lines, $font-size, $is-vert: $vertical-writing)
```

```
trailer($lines, $font-size, $property, $is-vert: $vertical-writing)
```

```
padding-trailer($lines, $font-size, $is-vert: $vertical-writing)
```

```
margin-trailer($lines, $font-size, $is-vert: $vertical-writing)
```

```
rhythm($leader, $padding-leader, $padding-trailer, $trailer, $font-size, $is-vert: $vertical-writing)
```

```
leading-border($width, $lines, $font-size, $border-style, $is-vert: $vertical-writing)
```

```
trailing-border($width, $lines, $font-size, $border-style, $is-vert: $vertical-writing)
```

```
horizontal-borders($width, $lines, $font-size, $border-style,  $is-vert: $vertical-writing)
```

```
h-borders($width, $lines, $font-size, $border-style,  $is-vert: $vertical-writing)
```

## License

MIT.

## Copyright

Copyright (c) 2013 Densho Channel  
<http://densho.hatenablog.com/>  
All rights reserved.
