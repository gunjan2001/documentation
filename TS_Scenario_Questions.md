# Questions:

**1. You have an object with a variety of properties, and you want to create a new type that includes only the properties whose values are of a specific type.**

```
type MyObjectType = {
  prop1: number;
  prop2: string;
  prop3: boolean;
  prop4: string[];
  prop5: Date;
};

type PropertiesOfType<T, U> = {
  [K in keyof T]: T[K] extends U ? K : never;
}[keyof T]; // this [keyof T]  is used to access the union of all keys of the type T .

type StringProperties = PropertiesOfType<MyObjectType, string>;
```

**2. You have a type that includes optional properties, and you want to create a new type that excludes those optional properties.**

- used Required Type.

```
type MyType = {
  prop1: number;
  prop2?: string;
  prop3?: boolean;
};

type NonOptionalType = Required<MyType>;
```

**3. You have a type with properties that can be both optional and nullable, and you want to create a new type that includes only the properties that are neither optional nor nullable.**

```
interface Demo{
    name:boolean;
    address:null;
    email?:string;
    phone?:number;
    salary?:number;
}

type NotNullAndOptional<T> = Pick<T,{[K in keyof T]:T[K] extends null  ? never : undefined extends T[K] ? never : K}[keyof T]>

type New = NotNullAndOptional<Demo>
```

4.  You have a function that accepts an object with various properties, and you want to ensure that only a subset of those properties can be modified. Which utility type would you use, and how would you define the type for the read-only properties?

```
type MyObject = {
  id: number;
  name: string;
  age: number;
  email: string;
};

type PartiallyReadOnlyObject<T,K extends keyof T> = Readonly<Pick<T,K>> & Omit<T,K>
type ReanOnlyName = PartiallyReadOnlyObject<MyObject, "name">;


```

5. You have a function that accepts an object with an unknown number of properties, and you want to infer the type of one specific property dynamically. Which utility type would you use, and how would you extract the type of the desired property?

```
type MyObject1 = {
  id: number;
  name: string;
  age: number;
};

function getPropertyType<T, K extends keyof T>(obj: T, prop: K): T[K] {
  return obj[prop];
}

const obj1: MyObject1 = {
  id: 1,
  name: 'John',
  age: 25,
};

const idType =  getPropertyType(obj1, 'id');   // number type

```

6.  You have an array of objects, and you want to group them based on a specific property value, creating a new type that represents the grouped objects. Which utility type(s) would you use, and how would you group the objects based on the property value?

```
type OriginalType = {
  id: number;
  category: string;
  name: string;
};

type GroupedObjects = Record<OriginalType['category'], OriginalType[]>;

const objects: OriginalType[] = [
  { id: 1, category: 'A', name: 'Object 1' },
  { id: 2, category: 'B', name: 'Object 2' },
  { id: 3, category: 'A', name: 'Object 3' },
  { id: 4, category: 'B', name: 'Object 4' },
  { id: 5, category: 'C', name: 'Object 5' },
];

const grouped: GroupedObjects = objects.reduce((acc, obj) => {
  if (acc[obj.category]) {
    acc[obj.category].push(obj);
  } else {
    acc[obj.category] = [obj];
  }
  return acc;
}, {} as GroupedObjects);

console.log(grouped)
```

**Output:**

```
{
  A: [{ id: 1, category: 'A', name: 'Object 1' }, { id: 3, category: 'A', name: 'Object 3' }],
  B: [{ id: 2, category: 'B', name: 'Object 2' }, { id: 4, category: 'B', name: 'Object 4' }],
  C: [{ id: 5, category: 'C', name: 'Object 5' }]
}

```
