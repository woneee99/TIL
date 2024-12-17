🤔 인터페이스는 js에는 없는데, 어떻게 하지?

### 인터페이스
```typescript
interface LabelVal {
    label: string;
    size: number;
}

function printLabel(labelObj: LabelVal) { // 변수: 선언타입
    console.log(labelObj.label + " " + labelObj.size);
}

let myObj = {size: 10, label: "Size 10 Object"};
printLabel(myObj);
```

### 선택적 프로퍼티
```typescript
interface SquareConfig {
    color?: string;
    width?: number;
}

function createSquare(config: SquareConfig): {color: string; area: number} {
    let newSquare = {color: "white", area: 100};
    if (config.color) {
        newSquare.color = config.color;
    }

    if (config.width) {
        newSquare.area = config.width * config.width;
    }
    return newSquare;
}

let mySquare = createSquare({color: "black"}); // width를 호출해도, 안 해도 상관없음
```
### 읽기전용 프로퍼티
```typescript
interface Point {
    readonly x: number;
    readonly y: number;
}

let p1: Point = { x: 10, y: 20 };
p1.x = 5; // 이렇게 재정의할 때 오류 발생
```

### 초과 프로퍼티 
```typescript
interface SquareConfig {
    color?: string;
    width?: number;
    [propName: string]: any; // 가지고 있지 않은 프로퍼티가 있으면, 에러 발생하기에 이를 피할 수 있는 방법
}

function createSquare(config: SquareConfig): { color: string; area: number } {
    let newSquare = {color: "white", area: 100};
    console.log(config.colour);
    return newSquare;
}

let mySquare = createSquare({ colour: "red", width: 100 } as SquareConfig);

```

### 함수 타입
```typescript
interface SearchFunc {
    (source: string, subString: string): boolean; 
}

let mySearch: SearchFunc; // 해당 인터페이스 사용 
mySearch = function(source: string, subString: string) { // 함수 타입 인터페이스는 다른 인터페이스처럼 사용 가능
    let result = source.search(subString);
    return result > -1;
}

console.log(mySearch("rexd", "x")); // true 출력
```

### 인덱서블 타입
```typescript
interface StringArray {
    [idx: number]: string;
}

let myArray: StringArray;
myArray = ["Bob", "Fred"];

console.log("myArray: " + myArray[1]); // Fred 출력
```

### 클래스 타입
1) static 타입
2) 인스턴스 타입


```typescript
interface ClockConstructor {
    new (hour: number, minute: number): ClockInterface;
}
interface ClockInterface {
    tick(): void;
}

function createClock(ctor: ClockConstructor, hour: number, minute: number): ClockInterface {
    return new ctor(hour, minute);
}

class DigitalClock implements ClockInterface {
    constructor(h: number, m: number) { }
    tick() {
        console.log("beep beep");
    }
}
class AnalogClock implements ClockInterface {
    constructor(h: number, m: number) { }
    tick() {
        console.log("tick tock");
    }
}

let digital = createClock(DigitalClock, 12, 17);
digital.tick();
let analog = createClock(AnalogClock, 7, 32);
analog.tick();
```

### 인터페이스 확장하기
```typescript
interface Shape {
    color: string;
}

interface PenStroke {
    penWidth: number;
}

interface Square extends Shape, PenStroke {
    sideLength: number;
}

let square = {} as Square;
square.color = "blue";
square.sideLength = 10;
square.penWidth = 5.0;
```

