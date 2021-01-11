# axios

TODO : real time search functionality in oscar or not
API to serve real time search that just lists out the categories 

* To clear node shell press `ctrl+l`
* Lets understand what HTTP headers really are:

## What are CORS

* CORS ( cross origin resource sharing ) is a specification by which two different servers can send request to each other. 
* Cross origin request
* `access_control_origin` header is responisble for that. 
* The origin `normal-website.com` invokes the following request

        GET /data HTTP/1.1
        Host: robust-website.com
        Origin : https://normal-website.com

The server on robust-website.com returns the following response:

        HTTP/1.1 200 OK
        ...
        Access-Control-Allow-Origin: https://normal-website.com

The browser will allow code running on normal-website.com to access the response because the origins match.


## Axios 

        axios.get("url",data).then((response)=> {}).catch((error) => {});

### Interceptors:

* The error handling method defined is local. if you want to intercept it locally, which can be done because a comon axios instance runs over all app. we can use :
        
            axios.interceptors.request.use( request => {... //always return request
            return request}, error => {...});

* Request and response are different.
* request will catch error if request can't be made, due to internet connectivity problem or any other problem.
* to catch the reponse use:

            axios.interceptors.response.use( response => {... //always return request
            return request}, error => {...
            return Promise.reject(error)});
            
 * getting rid of interceptor is also easy. Simply store the reference to the interceptor in a variable and call eject  with that reference as an argument, to remove it (more info: https://github.com/axios/axios#interceptors):

            var myInterceptor = axios.interceptors.request.use(function () {/*...*/});
            axios.interceptors.request.eject(myInterceptor); 


## Axios Default setup

* if there is a single url where request is being made to
* on index.js file

        axios.defaults.baseURL = 'myURL';

![](_v_images/20210106172351184_1293430373.png =776x)

## Creating Axios instance

![](_v_images/20210106172946065_1385465852.png =400x)
        

