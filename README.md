# React Workshop

## Dice

Simulate a six side dice (D6) roll.

Goal: 

- Learn how to use and update immutable states.
- Use simple conditional rendering (ternary).

1. Create a Dice.jsx component, import it to the App.jsx and display it.
2. Dice.jsx: Display a Button with a text "Roll".
3. Dice.jsx: If the user clicks on the "Roll" button, show a random number from 1 to 6 next to the button.
4. Dice.jsx: If the Dice is not clicked, first show a "Please press the Roll button." text.

Component hierarchy:

- App
  - Dice

## Dice History

Record the roll history of the dice rolls. Reuse the Dice.jsx from the previous example.

Goal:

- Learn how to lift a state up from the child component to the parent component.
- Update mutable data structures, like an array.
- Display lists with JSX elements.

1. Refactor App.jsx, Dice.jsx: Move the state to App.jsx, remove it from Dice.jsx. The new states must be an array of numbers in App.jsx.
3. Dice.jsx: The Dice component should notify its parent component when a new dice is rolled. It should pass the new roll's value to it. Use the `onRoll` property to communicate this change.
4. App.jsx: Handle the `onRoll` event. Collect the rolled number in a state (array).
5. App.jsx: Display the list (`<ul></ul>`) of the previously rolled numbers as a list items (`<li></li>`). Use the local rolls state from the App. 

Component hierarchy:

- App
  - Dice(onRoll)

## Extend the roll model

Goal:

- Learn how to pass down a state from parent to child.
- Adding new items to an array of objects.

1. Create a RollHistory.jsx component, import it to the App.jsx and display it.
2. App.jsx: Record the following properties of each dice roll (the state should be changed from array of numbers to array of objects), the event still the Dice.jsx component's onRoll:

- The number which is rolled by the Dice.jsx.
- The a boolean propery, indicated that the dice is collected or not.
- An ID, an increasing number on each new roll, started from 10.

2. RollHistory.jsx: move the list of rolls from App to this component, use a prop to pass down the rolls. 

Component hierarchy:

- App
  - Dice(onRoll)
  - RollHistory(rolls)

## Collect the dices

You can mark a dice collected with a button.

Goal:

- Updating states with an array of objects.
- Lifting up a state from an array.

1. RollHistory.jsx: Show a list of rolled numbers with a Button named "Collect" on each. Have an event handler property called onCollect. It should be triggered with the ID of the given dice roll, when the user clicks on the "Collect" button.
2. App.jsx: handle the onCollect event, modify the list of rolls' collected property according to it. 
3. RollHistory.jsx: If roll is collected, show its number with ~~strikethrought~~ style. The Collect button must be disabled. If a roll is collected, it should be kept collected afterwards.

Component hierarchy:

- App
  - Dice(onRoll)
  - RollHistory(rolls, onCollect)

## Remove dice

Remove a dice from a roll history. 

Goal:

- State handling, remove a given item from a state with list of objects.

1. App.jsx: Add a Remove button to each roll in a list. Use the onRemove prop as an event handler of the RollHistory component to nofity the parent component, when a user clicks on a paricular Remove button. Send the ID of the given roll to the event handler's param.
2. App.jsx: When the RollHistory.jsx's onRemove event is happened, remove the given roll from the state.
3. App.jsx: Only the non collected rolls can be removed.

Component hierarchy:

- App
  - Dice(onRoll)
  - RollHistory(rolls, onCollect, onRemove)

## Yahtzee

Implement a simplified [yahtzee](https://en.wikipedia.org/wiki/Yahtzee) game from this state. Freestyle.
You can reuse the components from the previous exercises.

Goal: 

  - Play a little bit around what you have learned.

Features, obligatory:

- At most 6 rolls you have. If 6 rolls are displayed, the Roll button should be disabled. If you remove a dice, you can add a roll again. You can not remove a collected dice.
- If a dice [category](https://en.wikipedia.org/wiki/Yahtzee#Lower_section) is collected, show its name in a new component. (3 of a kind, 4 of a kind, yahtzee, full house support is enough). In a case of multiple category match, the category with the highest score should be displayed.
- Support restart of the game.

Component Hierarchy:

- App
  - Dice(onRoll)
  - RollHistory(rolls, onCollect, onRemove)
  - CategoryResult(rolls)

Extra features ideas:

- The user remove at most 3 dices. Display them how many dices still have.
- Show the scores next to detected category.
- Support all roll categories.
- Support automatic reroll of all non collected components. The remove 3 dices limit can be skipped, but you can reroll only 3 times.
- Display dice faces instead of numbers.
