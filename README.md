# react-use-debounced

Custom useDebounced for React Hooks

```javascript
const [value, setValue] = useState("");

const useDebounce = (value, delay) => {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const handler = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);
    return () => {
      clearTimeout(handler);
    };
  }, [value]); // eslint-disable-line react-hooks/exhaustive-deps

  return debouncedValue;
}

// Usage
const debouncedSearch = useDebounce(value, 500);
```
