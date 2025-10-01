# ts_linq_base

Linq methods for Array in Typescript

# Installation



```bash
npm install ts_linq_base
```

# Usage

In your entrypoint file, use: 
### Sample Usage

```typescript
// Sample arrays
let stringArray = ["adriano", "marino", "balera", "camila", "juliana", "andre"];
let numberArray = [1, 5, 3, 7, 9, 3, 6];
let dateArray = [new Date('2023-01-01'), new Date('2025-01-01'), new Date('2021-01-01')];
let objectArray = [
       new Person("adriano", 950, Gender.MALE),
       new Person("camila", 25, Gender.FEMALE),
       new Person("juliana", 30, Gender.FEMALE),
       new Person("andre", 30, Gender.MALE)
];
```

### Where
```typescript
stringArray.Where(s => s.startsWith("a")); // ["adriano", "andre"]
objectArray.Where(s => s.Name.startsWith("a")); // [Person("adriano",950,MALE), Person("andre",30,MALE)]
numberArray.Where(s => s > 2); // [5,3,7,9,3,6]
dateArray.Where(s => s > new Date("2022-01-01")); // [2023-01-01, 2025-01-01]
```

### Count
```typescript
objectArray.Count(); // 4
numberArray.Count(s => s > 2); // 5
```

### Any
```typescript
stringArray.Any(); // true
stringArray.Any(s => s.startsWith("a")); // true
```

### All
```typescript
stringArray.All(s => s.startsWith("a")); // false
```

### FirstOrDefault
```typescript
stringArray.FirstOrDefault(); // "adriano"
stringArray.FirstOrDefault(s => s == "camila"); // "camila"
```

### First
```typescript
numberArray.First(); // 1
numberArray.First(s => s > 5); // 7
```

### Last
```typescript
numberArray.Last(); // 6
numberArray.Last(s => s < 5); // 3
```

### OrderBy
```typescript
stringArray.OrderBy(); // ["adriano","andre","balera","camila","juliana","marino"]
objectArray.OrderBy(p => p.Name); // [adriano, andre, camila, juliana]
objectArray.OrderByDescending(p => p.Name); // [juliana, camila, andre, adriano]
```

### GroupBy
```typescript
objectArray.GroupBy(u => u.Gender);
// MALE: [adriano, andre]
// FEMALE: [camila, juliana]
```

### Aggregate
```typescript
numberArray.Aggregate(); // 34
```

### Select
```typescript
numberArray.Select(s => s ** 2); // [1,25,9,49,81,9,36]
objectArray.Select(s => s.Age); // [950,25,30,30]
numberArray.Select(s => new Person("Adriano", s, Gender.MALE)); // [Person(1), Person(5), Person(3), ...]
```

### SelectMany
```typescript
objectArray.SelectMany(s => s.DOCs); // concatena todos os arrays DOCs em um único array
```

### Skip
```typescript
numberArray.Skip(3); // [7,9,3,6]
```

### Take
```typescript
numberArray.Take(3); // [1,5,3]
```

### Sum
```typescript
[1,2,3,4,5].Sum(); // 15
objectArray.Sum(s => s.Age); // 1035
```

### Max
```typescript
[1,2,3,4,5].Max(); // 5
objectArray.Max(s => s.Age); // 950
```

### Min
```typescript
[1,2,3,4,5].Min(); // 1
objectArray.Min(s => s.Age); // 25
```

### Avg
```typescript
[1,2,3,4,5].Avg(); // 3
objectArray.Avg(s => s.Age); // 258.75
```

### Distinct
```typescript
[1,2,2,3,4,5,5].Distinct(); // [1,2,3,4,5]
```



## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)