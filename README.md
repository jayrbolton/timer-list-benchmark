# timer-list-benchmark

> The Timer List Benchmark is a usability benchmark for GUI libraries and frameworks

When you're comparing front-end UI libraries and frameworks, it's nice to have a reference point. TodoMVC falls very short when it comes to testing how well a library can handle modular, composable, and scalable components.

This benchmark is designed to be a much better and more thorough test of UI frameworks without significantly increasing the work to implement an example.

General instructions
* Walk through each phase below, creating the given UI and testing it against the requirements
* You don't need to design or style anything.

## Phase 1 - a countdown timer

[demo](/todo)

Create a countdown timer component with these elements:
* An input where you can enter timer duration (in seconds)
* A start/stop toggle button
* A "reset" button
* Some text displaying time elapsed
* Some text displaying total duration

Requirements:
* The duration input should only accept numbers >= 1
* The start/stop button should read "Stop" when the timer is running, and "Start" when it is paused.
* The reset button should be disabled when the elapsed time is 0 and the timer is not running
* Clicking the reset button should set the elapsed seconds to zero and pause the timer
* The elapsed time text should show one-hundredths of a second with two decimal places
* When the elapsed seconds reaches the duration, then the timer should stop, and:
  * The start/stop button should be disabled
  * The reset button should be enabled

Example file structure:
* `timer.js` exports the code for the component
* `timer-page.js` renders a timer to the page

## Phase 2 - a timer collection

[demo](/todo)

Now we reuse the code you wrote for Phase 1 for a list of timers.

Elements:
* A duration input
* An "Add timer" button that appends a new timer to the page with the given duration
* Text for "total duration" that aggregates the duration of every timer on the page.
* A "Reset All" button that resets all timers on the page
* Next to each timer: a "Remove" button that removes each timer from the page
* Two initial timers appended to the page with random durations between five and ten seconds.
* Each timer should show, in addition to seconds elapsed and duration, the total duration.

Requirements
* **You must reuse the code that you wrote for Phase 1 without changing it**
* The "Reset All" button should be disabled when all timers are reset.
* The duration input should only accept numbers >= 1
* The "Total elapsed" and "Total duration" text should update whenever any timer updates
* The "Add timer" button should create a new timer with the duration from the duration input

Example file structure:
* `timer-list.js` is the code for the component
* `timer-list-page.js` renders the timer list to the page

## Phase 3 - a collection of collections

Finally, make a list of lists of timers. You can add new timer lists, name them, and remove lists.

Elements:
* An input field for "List name"
* An "Add timer list button"
* Text that shows the count of the total number of timers running in all the lists
* A remove button next to each list

Requirements:
* **You must reuse the code from Phase 2 without changing it**
* Whenever a timer stops, starts, finishes, or resets, the total timers running count at the top of the page should be updated.

Example file structure:
* `timer-list.js` is the code for the component
* `timer-list-page.js` renders the timer list to the page
