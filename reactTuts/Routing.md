# Routing

## Setting Up

![](_v_images/20210107185716317_123029522.png)

## Multiple pages 

* Main component that requires routing should be enclosed in Browser Router

![](_v_images/20210107193020276_1257687911.png)


![](_v_images/20210107192250842_965772507.png)

![](_v_images/20210107192918326_1229676321.png)

* instead of  render use component to route to component
* Multiple Components can have same route and they all will render
![](_v_images/20210107193220483_490451191.png)

* instead of anchor tags, React router provides with a link component that makes sure that we prevent the default behaviour. `e.preventDefault()` but on steroids.

![](_v_images/20210107193858014_709716233.png)

* When ever route is successful. The component that is loaded for that route receives a props, that is injected by react router itself. 

* The router targets a component and receives a prop but its child components don't receive those props. To be able to access those props.
    * Either `{...this.props}` as a attribute to the Child Container.

            <ChildContainer {...this.props} />
    * Or use `withRouter` Higher Order Component.

* convert absolute path to relative path
* ![](_v_images/20210107201340741_2053146199.png)

* For a navBar link use `navLink` instead of `link`. for Styling purpose.

* Passing in Route Parameters : 
    * Add `:ParamName`. Object will be added later as `this.props.match.params.ParamName`.
        
![](_v_images/20210108141108377_1049862879.png)

![](_v_images/20210108141340584_1611930303.png)
		
* Want to load only one route. use . makes sure one router is loaded and another one is no longer loaded.~~~~
    
    ![](_v_images/20210108174948552_1860158009.png)

* the `:id` part moves in as `this.props.match.params.id`

## Nested Route

* If a main component is inside a `<BrowserRouter/>` then it is eligible to be placed anywhere.
* Where ever router stays. or which ever component Router resides . The section Router doesn't touch will keep on rendering. Router doesn't update everything.
* Nested Routes are required if a routed component requires a route. Routed components section will remain untouched and will render. 
* Exact can also be handy here.

## Redirect

![](_v_images/20210110193731989_818149595.png)

### Conditional Re-routing

* For a conditional redirect, normal state based contionals will work.
![](_v_images/20210110193938821_674831915.png)


## Guards

* Authenticated or Not?
* Generic state based conditional approach

## 404 case

* Don't add path to `Route` . it will load if 404 case is met
* 


## React suspence

* won't work for server side rendered page
 * Works for 16.6+
![](_v_images/20210110205321297_1779411269.png)
* add `Suspence` to import from react

![](_v_images/20210110205421423_1057936840.png)


* want to setup where url is `exampl.com/my-app` instead of  `exampl.com/`

![](_v_images/20210110205953738_508077980.png)