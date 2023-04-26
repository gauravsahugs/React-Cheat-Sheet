useCallback

The useCallback hook is used when you have a component in which the child is rerendering again and again without need.

const memoizedCallback = useCallback(
() => {
doSomething(a, b);
},
[a, b],
);
