I will be discussing the exercise 16_lifetimes2

```
fn longest(x: &str, y: &str) -> &str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}

```
this code doesn't compile because the lifetimes of x and y could be different  and that could cause issues if one (or more) is out of scope when the reference is returned, which could point at invalid memory and break.

changed the line to 
```
fn  longest<'a>(x:  &'a  str, y:  &'a  str) ->  &'a  str {
...
}```
