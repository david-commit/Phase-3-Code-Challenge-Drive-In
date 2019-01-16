# Object Relations Assessment

## Your Task

For this challenge, you have been given the job of creating a command line interface for your local drive-in movie theater, Happy's Sunset Drive-In! You have been asked to create a tracking tool that allows employees to know how many cars are at each movie screen.  The drive-in has many screens, and each screen can have many cars.  For the safety of all viewers, there is a limit to the number of cars that can be at a movie screen.  

## Notes

Your goal is to build out all of the methods listed in the deliverables and connect the required classes to a command line interface.

Do your best to follow Ruby best practices. For example, use higher-level array methods such as `map`, `select`, and `find` when appropriate in place of `each`

We've provided you with a tools/console.rb file, so you will be able to test out the methods that you write here.

**To Submit** - once you've completed all the deliverables, please copy/paste your three class definitions into the `solution.rb` file. Please don't submit the lab until we give you the signal.

## Deliverables

Implement all of the methods described below:

## Basic Methods and Attributes

### `DriveIn`

A drive-in should be initialized with a `name` as a string. The name **cannot** be changed after the drive-in is initialized.

---

### `MovieScreen`

A movie screen should be initialized with a `movie` object, `capacity` (as an integer), and a `drive_in` object.

+ `MovieScreen.all_screens`
  + Returns an array of all movie screens that have been created.

---

### `Car`

A car should be initialized with a `passenger_count` (as an integer).

+ `Car#passenger_count`
  + Returns the number of passengers in the car.
+ `Car#movie_screen=`
  + Assigns a screen object to a particular car. **Note:** this might happen _after_ a car has already been created.
+ `Car#movie_screen`
  + Returns the movie screen that a particular car is associated with
+ `Car.all`
  + Returns an array of all car instances that have been created.

---

## Aggregate Methods

### `MovieScreen`

+ `MovieScreen#cars`
  + Returns an array of all cars currently at _this_ movie screen.
+ `MovieScreen#at_capacity?`
  + Returns a boolean. The return will be true if the number of cars at _this_ movie screen is the same as its capacity.
+ `MovieScreen#add_car`
  + Associates a car object with _this_ movie screen.
    + If the movie screen is _not_ at capacity, it associates the objects and returns the string "Enjoy!".
    + If the movie screen is at capacity, return the string "Sold Out!"
+ `MovieScreen#how_many_viewers?`
  + Returns the total number of people viewing the movie

---

### `DriveIn`

+ `DriveIn#screens`
  + Returns an array of all movie screens at _this_ drive-in.
+ `DriveIn#cars_with`
  + Accepts a string as a single argument.
  + Returns an array of all cars at _this_ drive-in with a given number of passengers inside.
+ `DriveIn#full_house?`
  + Returns true if all movie screens at _this_ drive-in are at capacity.
+ `DriveIn#whats_playing`
  + Returns an array of all the names of the movies playing at _this_ drive-in.
+ `DriveIn#available_movies`
  + Returns a hash with a top-level key representing every available movie at _this_ drive-in.
  + Each key will point to _another hash_ with two keys:
    + `available_spots`
      + Should represent the number of spots available at this movie.
    + `people_watching`
      + Should represent the total number of people watching this movie.

For example:
```ruby
{
  the_shawshank_redemption: {
    available_spots: 10,
    people_watching: 30
  },
  spider_man_2: {
    available_spots: 0,
    people_watching: 150
  }  
}
```

---
