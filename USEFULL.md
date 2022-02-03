### @ (alternative - v-on:)
```
listen events
by default when we use methods like:
smth() - vue gives us event and we check like event.target.value (for example)
but we can pass value manualy: smth($event.target.value)
```

### :smth
```
add dynamical data
```

### computed
```
is better than methods, because computed done smth (what you have wriiten) only once
we can't pass any arguments, because computed is like a simple variable
```

### v-for
```
just a simple foreach in vue
you also should pass :key props
you can also iterating by object's entries like that: 
(value, key, index) in smth[any index]
```

### watch(newValue, oldValue)
```
literally looking after some changes and do smth
it must have the same name the field we are looking after
```