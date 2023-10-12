# MYLINQ

Linq methods for Array in Typescript

# Installation



```bash
npm install mylinq
```

# Usage

In your entrypoint file, use: 


```typescript
import 'mylinq';
```
### Sample arrays

```typescript
 let stringArray = ["adriano", "marino", "balera", "camila", "juliana", "andre"];
 let numberArray = [1, 5, 3, 7, 9, 3, 6];
 let dateArray = [new Date('2023-01-01'),new Date('2025-01-01'), new Date('2021-01-01')]
 let objectArray = 
 [
        new Person("adriano", 950, Gender.MALE),
        new Person("camila", 25, Gender.FEMALE),
        new Person("juliana", 30, Gender.FEMALE),
        new Person("andre", 30, Gender.MALE)

 ];
```

### Where
```typescript
let i = stringArray.Where(s => s.startsWith("a"));   
        
let c = objectArray.Where(s => s.Name.startsWith("a"));       

let u = numberArray.Where(s => s > 2);

let d = dateArray.Where(s => s > new Date('2022-01-01'));
       

```


### Count
```typescript   
let c = objectArray.Count();       

let u = numberArray.Count(s => s > 2);

```


### Any
```typescript   
let i = stringArray.Any();

let u = stringArray.Any(s => s.startsWith("a"));

```

### All
```typescript   
let u = stringArray.All(s => s.startsWith("a"));

```


### FirstOrDefault
```typescript   
stringArray.FirstOrDefault();

stringArray.FirstOrDefault(s => s == "camila");       

```

### OrderBy 
```typescript   
let i = stringArray.OrderBy();

let u = objectArray.OrderBy(p => p.Name); 

let v = objectArray.OrderByDescending(p => p.Name);
```

### GroupBy
```typescript   
let g = objectArray.GroupBy(u => u.Gender);
```

### Aggregate
```typescript   
 let g = numberArray.Aggregate();
```

### Select
```typescript   
let g = numberArray.Select(s => s ** 2);  
let u = objectArray.Select(s => s.Age);
let p = numberArray.Select(s => new Person("Adriano", s, Gender.MALE));
```


### SelectMany
```typescript   
let g = objectArray.SelectMany(s => s.DOCs);      
```

### Sum
```typescript   
[1,2,3,4,5].Sum(); 
objectArray.Sum(s => s.Age);      
```

### Max
```typescript   
[1,2,3,4,5].Max();
objectArray.Max(s => s.Age);       
```


### Min
```typescript   
[1,2,3,4,5].Min(); 
objectArray.Min(s => s.Age);      
```


### Avg
```typescript   
[1,2,3,4,5].Avg(); 
objectArray.Avg(s => s.Age);      
```



## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)