# 0. Call useState Multiple Times in One Component

[Video Link](https://egghead.io/lessons/react-call-usestate-multiple-times-in-one-component)

## Questions(s)
* How to store more than one piece of state in a component?

You can track of two pieces of state in this App using the useState hook.

You'll start by setting how much water you'll be keep track of and a setter function of ```<setOuncesWater>```  these values will be filled by calling ```<useState>``` and passing in 8.

The second piece of state keeps track the grams of coffee we have. ```<setGramsCoffee>``` is the setter function and set ```<useState>``` and pass in 13.

You can name the setter functions anything you want, but it is common to start these function names with the word set.

Add buttons that render what ```<useState>``` is set as. 

Add onClick handlers to your buttons that calls ```<useState()>``` and pass in how you want the state to change

```javascript
function App() {
  const [water, setOuncesWater] = useState(8);
  const [coffee, setGramsCoffee] = useState(13);

  return (
    <div>
      <h1>Coffee Maker</h1>
      <span aria-hidden>☕</span>
      <h2>Water</h2>
      <button
        onClick={() => setOuncesWater(water + 1)}
      >
        {water} oz
      </button>
      <h2>Coffee</h2>
      <button
        onClick={() => setGramsCoffee(coffee + 1)}
      >
        {coffee} g
      </button>
    </div>
  );
}
```





## Resources

















