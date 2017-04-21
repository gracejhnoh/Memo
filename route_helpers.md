# Rails URL Helpers



### Basically... make URLS cleaner and simpler to understand

-------------------

#### Hard Coded Paths: slow, prone to error, & a lot of work to change
    e.g. `"/posts/#{@user.id}"`
         `"/photos/:id/edit"`

#### Route Helpers: faster & easier to change if the route destination changes
    e.g. `post_path(@user.id)`
         `edit_photo_path(:id)`

------------------
### Benefits to using Route Helpers

1. are methods, not strings
    - more dynamic (in other words... even if something with the route needs to be changed, there's a high chance that the code won't need to be touched at all)

2. cleaner & more readable than hard coded paths
    - help clean up view and controller
    - NOTE: cannot be used within model 

3. arguments can be more easily and readily passed in to methods (route helpers), unlike hard coded paths, which require string interpolation
>    e.g. 
>    
>        `"users/<%= user.id %>?opt_in=true"`
>
>        `user_path(user, opt_in: true)`

4. Automatically translate into HTML-friendly paths
    - characters like spaces, '&', '%', etc. are converted so that browsers can read them 

-----------------
### In your console... 

- simply enter "rails routes"
- for whatever path you need, take the prefix, add `_path` and there you have it... a route helper!

![alt text](https://github.com/gracenoh153/Memo/blob/master/Screen%20Shot%202017-04-20%20at%208.22.30%20PM.png "Rails Routes in Console")

### Examples: 
1. `users_login_path` vs `"/users/login"`
2. `edit_user_path` vs `"/users/:id/edit`
2. `edit_experiment_path` vs `"/experiments/:id/edit"`

----------------

Sources:
- https://learn.co/lessons/rails-url-helpers-readme
- http://guides.rubyonrails.org/routing.html#path-and-url-helpers