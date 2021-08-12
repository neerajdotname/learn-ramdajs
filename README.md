# Nov 24

#### Solution 1

https://jsfiddle.net/zojrxyfc/1/


#### Solution 2

https://jsfiddle.net/zojrxyfc/3/

#### Solution 3

https://jsfiddle.net/zojrxyfc/5/

# Nov 27


Solution1 :  https://jsfiddle.net/rtLgaks8/2/

Solution 2 : https://jsfiddle.net/rtLgaks8/3/


### Another similar problem

Solution 1 : https://jsfiddle.net/eaytmd9r/1/

Solution 2 : https://jsfiddle.net/eaytmd9r/2/

# Nov 28

Solution 1 : https://jsfiddle.net/nrkfgLge/1/

Solution 2 : https://jsfiddle.net/nrkfgLge/2/

# Dec 4

https://www.youtube.com/watch?time_continue=500&v=JRzly-t4Boc

https://www.youtube.com/watch?v=F6yyrVJhGak

# Dec 8

https://jsfiddle.net/wLs35js9/1/


https://jsfiddle.net/8xjjwv65/1/

# Dec 11


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

## Case 3

https://github.com/ramda/ramda/issues/1642


## Problem 2


#### pointfree solution

https://jsfiddle.net/zojrxyfc/7/
