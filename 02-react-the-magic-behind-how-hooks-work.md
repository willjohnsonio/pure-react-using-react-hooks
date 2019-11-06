# 02. The "Magic" Behind How Hooks Work

[Video Link](https://egghead.io/lessons/react-the-magic-behind-how-hooks-work)

## Questions
* What is React doing with hooks behind the scenes?
* What are the rules for using Hooks?

Before React calls a component it creates an array of hooks that lives alongside the component instance. React keeps an index of this array.

Everytime you call a hook it will take up the first slot of the hooks array, eith the value you passed as default.

The index then moves to the next slot in the hooks array ready for the next hook.

If there is no next hook, the index is going to reset and React is going to re-render that component. 

If you have mulitple pieces of state. (in the video example is 3)

You have our array of hooks and the index is set to 0. Then React renders the component for the first time.

The first ```<useState>``` takes up the first slot. Then the index moves down.
 
The second ```<useState>``` takes up the second slot, and the index moves down.

The third ```<useState>``` takes the third slot and the index moves down again.

If you type a D into the username box. That first slot is replaced with a D instead of empty string and then the component re-renders again. 

The index is going to reset. The first ``<useState>``` is going to pull out that D, the second call is going to pull out the empty string, and the third call's going to pull out false.

This is how hooks are able to retain state between renders

```javascript
const LoginFOrm = () => {
    const [username, setUsername] = useState('');
    const [password, setPassword] = useState('');
    const [remember, setRememberMe] = useState(false);

    return (
        <form>
        <label htmlFor="username">Username</label>
        <input 
        value={username}
        onChange={e => setUsername(e.target.value)}>
        id = "username"
        type="text"
        />
    )
}
```

 



**Rules of React Hooks**
1. You can't put hooks inside loops, conditionals, or nested functions

2. You can only call hooks from function components or custom hooks. You can't call it from classes.

3. Custom hook names should start with the words use

## Resources
[Using the State Hook](https://reactjs.org/docs/hooks-state.html)

[React Hooks Syntax.fm Episode](https://syntax.fm/show/092/react-hooks)
















