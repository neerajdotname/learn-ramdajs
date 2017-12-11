
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


## Case 2

#### Original

```
 componentDidMount() {
   const { addProject } = this.props;
 
    const projects = getProjectsFromStorage();
    projects.forEach(project => addProject(project));
 }
```

#### Better

```
componentWillMount = R.pipe(
     getProjectsFromStorage,
     R.forEach(this.props.addProject)
);
```
