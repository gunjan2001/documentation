##1 Custom hook question:

```
const MenuCard = (props) => {
  const [menuData,setMenuData] = useState([]);
  
  if(props.isIndian){
    const data = useGetHotelMenu(true)
    setMenuData(data);
  }
 
  if(!props.isIndian){
    const data = useGetHotelMenu(false)
    setMenuData(data)
  }
 
  return (
    <>
    {
      menuData.map(item => <p>{item}</p>)
    }
    </>
  )
}

<MenuCard isIndian />

const useGetHotelMenu=(isIndian) => {
 
  if(isIndian){
    return ['a','b','c']
  }
  else{
    return ['d','e','f']
  }
}
```

### Output:
```
Error Reason: hooks cannot call inside any conditions or loops.
```

### Rules of custom hooks:

- 🔴 Do not call Hooks after a conditional return statement.
- 🔴 Do not call Hooks in event handlers.
- 🔴 Do not call Hooks in class components.
- 🔴 Do not call Hooks inside functions passed to useMemo, useReducer, or useEffect.
- 🔴 Do not call Hooks inside try/catch/finally blocks.
