# 01. Use the useState Hook to Add State to a Function Component

[Video Link](https://egghead.io/lessons/react-use-the-usestate-hook-to-add-state-to-a-function-component)


 To make ```<StepCounter>``` interactive, you're going to use the useState hook. Import useState from React. At the top of ```<StepCounter>```, call ```<useState()>```. Pass in the initial state of 0.

 UseState is going to return an array with two elements. can Destructure that array into two variables, called steps and setSteps. Then render the steps inside the ```<StepCounter>``` component.

 ```javascript
const StepCounter = () => {
  const [steps, setSteps] = useState(0);
  return (
    <main>
      <span aria-hidden>👟</span>
      <div>
        You've walked {steps} steps so far today.
      </div>
      <button>Record a Step</button>
    </main>
  );
};
 ```

When the React renders the ```<steps>``` the first time, it will initialize the number we pass into ```<useState>```, and we're rendering that here. 

It's also giving us the ```<setSteps>``` function so that we can change the steps and re-render the component.

Add a ```<onClick>``` handler on the button and pass it an arrow function. When the button is clicked, it will call ```<setSteps>``` and pass in step = 1.

```javascript
const StepCounter = () => {
  const [steps, setSteps] = useState(100);
  return (
    <main>
      <span aria-hidden>👟</span>
      <div>
        You've walked {steps} steps so far today.
      </div>
      <button onClick={() => setSteps(steps + 1)}>
        Record a Step
      </button>
    </main>
  );
};
```

When you click the button count increases. React is going to re-render this component. The call to useState it's going to return the latest value of state.

Even though we're passing in 100 to ```<useState>```, because this only affects the first render. Every time after that, we're going to get the current value out.

## Resources
[Using the State Hook](https://reactjs.org/docs/hooks-state.html)

[React Hooks Syntax.fm Episode](https://syntax.fm/show/092/react-hooks)
















