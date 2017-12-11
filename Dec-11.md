
## Case 1

#### Original 

```
const dispatchStepPending = step => dispatch(markStepPending(step.id));
```

#### Better

```
const dispatchStepPending = R.compose(
     dispatch,
     markStepPending,
     R.prop('id')
);
```
