# Problem Modeling and User Stories

## Learning Objectives

- Given a desired end-result, identify the bare minimum attributes necessary to make that end-result appear to have been met.
- Convert user stories into actionable pseudocode.

## Framing

This is going to be a code-free "think like a programmer" class. Please close your computers. You will not need them for the duration of the class.

## Exploration 1: Button (5 / 5 min)

[Display this page.](examples/button.html)

#### Q. What are we looking at?
> A button being pushed.

#### Q. Are we looking at a *real life* button being pushed?
> Obviously not.

#### Q. So how do you know it's a button?
- It's red
- It's round
- It's shaded
- It says "push"

### You Do (1 minute)

#### With the people at your table, identify what *specifically* tells you when the button has been "pushed".

- The bottom border shrinks
- The top border grows
- The background color darkens
- The text moves down a little

## Re-framing (5 / 10 min)

We try to code things that reflect the real world. Apple gave my computer a desktop and folders. Mario gave me a universe to run around in. For your [projects](https://github.com/ga-dc/wdi8-project1-gallery), several of you made webpages that looked like a wooden table with playing cards on it.

I saw several students Googling "how to flip a card" in Javascript, and getting bogged down in 3D engines and all sorts of very complicated things.

The more you try to stay in reality when coding, the more difficult coding can become. This is the same with writing books and poetry and painting: if you try to be 100% realistic, you will never finish.

Good developers strike a balance: they provide the bare minimum code necessary to create a sense of a specific reality.

## Faking It (10 / 20 min)

[Display General Assembly on Google Maps.](https://www.google.com/maps/place/General+Assembly+Washington+DC/@38.9048728,-77.0339908,17z/data=!4m2!3m1!1s0x89b7b7bfc2a12169:0x21c1233b00cff054)

### What is south of this image?

In real life, the answer is the White House. In the computer world, the answer is "nothing".

We have a perception of moving around a map, like we would in real life. But to have the entire world map loaded would take impossible amounts of memory.

What's *really* happening is that Google is showing a tiny portion of the world map. When the user clicks and drags the mouse a certain amount, Google loads an additional tiny portion of the map.

![Beta Brite](betabrite.jpg)

### The text on this sign isn't *actually* moving.

Small lights are turning on and off in a way that creates the illusion of moving.

![Super Mario](mario.jpg)

### What's behind Mario?

Nothing. Not even nothing. That's like asking what's outside our Universe.

The view of Mario's universe is created as it's necessary.

On computers, if a tree falls in a forest and no-one's around to hear it, it really *doesn't* make a sound.

### Computers are just little boxes of lights

![Obligatory XKCD](computer_problems.png)

## Exploration 2: Flying (10 / 30 min)

[Display this page.](examples/flying.html)

### You Do (5 minutes)

With your table answer these questions:

#### Q. What are we looking at?
#### Q. What's the nearest thing on the page? Furthest?
#### Q. What visual cues tell you what each thing is?
#### Q. As literally and technically as possible, describe what's happening on this page.

### Reflection

## Exploration 3: If it looks like a duck... (10 / 40 min)

[Display this page.](examples/duck.html)

### You Do (3 minutes)

With your table, discuss:

- Which of these looks most like a duck?
- What do the duck-looking ones have in common?

### You Do (3 minutes)

- What is the minimum necessary for something to look like a duck?

### Reflection

## User stories (10 / 50 min)

In "Agile" methodology, user stories describe every sequence of events a user may encounter when working with your app.

You brainstorm a bunch of user stories, and then select the ones that are most essential. When a user can complete all of these stories using your app, your app is considered complete.

Then, you can create additional user stories.

> This strongly correlates to test-driven development (TDD), which we'll talk more about in future weeks.

**You just created user stories for a duck.** That is: you defined what a user should experience in your creation in order for it to be considered a "complete" duck.

## BREAK (10 / 60 min)

## *User* stories versus *code* stories (10 / 70 min)

User stories describe what the user should be able to do. User stories **do not say anything about code.** "Code stories" is pseudocode.

#### Q. Why should you write user stories before you write code stories?

What's most important in a program is its perception by other people. What's second-most important is your code.

This is true of relationships as well: If you constantly hurt people's feelings, the fact that your intentions are always good doesn't really make a difference.

This is also true in business: If Facebook's users all believe their data is secure, whether or not their data is *actually* secure doesn't impact Facebook's business at all. *Actually* keeping your data secure is secondary to making it *look* secure: it's a means to an end. In order to maximize profit, Facebook will do the bare minimum necessary to ensure its users continue to believe their data is secure.

## We Do: User Stories for Concentration (20 / 90 min)

My first stab at the user stories for the game of concentration:

- When the user begins a game, the cards are face-down
- The user can turn over cards
- If two cards are face-up, and they match, the user leaves them face-up
- If two cards are face-up, and they don't match, the user turns them face-down

Now I'll start moving my user stories toward being code stories. To do this, I'll define some key *things* and *actions* in my user stories. For each one, I need to consider what the bare minimum is to achieve this effect:

| User story | Code story |
| --- | --- |
| Begins a game | The page loads |
| Card | A div |
| Face-down | The div has no text |
| Face-up | The div has text |
| Turn over | A card is clicked |
| Match | Two divs have the same text |
| Leaves them | Nothing happens |

### Tips for User-to-Code Stories

- If a user story is "nothing happens", it has no code story. There is no code for "nothing happens".
- My instinct to make a div go from "has text" to "no text" is to delete the text. But deleting and then replacing data is time-consuming and annoying. Why not just hide the div's text?
- Similarly, my instinct to make a click go from "does something" to "does nothing" is to remove its event listener. But deleting and replacing event listeners is time-consuming and annoying. Why not just put an `if` inside the event listener so it always fires, but only does stuff under certain conditions?

With this in mind, my user stories become:

- When the user loads the page, the values on all divs are hidden
- If the user clicks on a div with a hidden value, the value is revealed
- If the values of two divs are revealed, and their values are not the same, their values are hidden

Now I can turn my user stories into pseudocode. I'll use "when" for events, which will remind me to use event listeners:

```
When the page loads, the values on all divs are hidden
When a div is clicked
  If its value is hidden
    Its value is revealed
    If another div is already revealed
      If the other revealed div has a different value
        Both revealed divs' values are hidden
```

## You Do: User Stories for [Final Countdown](https://github.com/ga-wdi-exercises/final-countdown) (20 / 110 min)

Without looking at the prompt for Final Countdown, create user stories for it and convert them to code stories.

## You Do: User Stories for ATM (20 / 130 min)

[ATM application](https://github.com/ga-wdi-exercises/atm)

## Resources

- [Further "faking it" with old school graphics](https://www.youtube.com/watch?v=Tfh0ytz8S0k): A fascinating YouTube video
- [Making of Crash Bandicoot](http://all-things-andy-gavin.com/2011/02/04/making-crash-bandicoot-part-3/): How they faked the first 3D gaming world
- [How to wireframe](https://www.gliffy.com/uses/wireframe-software/)
