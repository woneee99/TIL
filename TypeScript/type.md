## 기본 타입

### 불리언 (Boolean) 
```typescript
let isDone: boolean = false;
```

### 숫자 (Number) 
```typescript
let hex: number = 0xf00d;
```

### 문자열 (String) 
```typescript
let fullName: string = `jwhwang`;
let sentence: string = `Hello, my name is ${ fullName }`;
```

### 배열 (Array) 
```typescript
let list: number[] = [1, 2, 3];
```

- 제너릭 배열 타입 가능
``` typescript
let arraylist: Array<number> = [1, 2, 3]; 
arraylist.push(4);
```

### 튜플 (Tuple) 
```typescript
let x: [string, number];
x = ["n", 2];
x.push(2);
```
