# React State Workshop

## Setup

- Use this template to create a new repo in your github account.

It is a simple Create React App install and start it as usual.

`npm install`

`npm start`

## Goal

The goal of this workshop to practice the state handling and state sharing between components in React.

## Tasks

- Do the tasks one by one.
- If you get stucked, check the background material's links

- components

### 1. Show a Dice

#### Goal

- Create a new component.
- Pass down data to the child component through props.

#### Tasks

Create a single `Dice` component. It should display a single number within a `<h2>` tag.

- [ ] A separate `Dice` component should be created.
- [ ] A `Dice` component must show a number given by a prop.
- [ ] A `Dice` component must be called from the `App`.

#### Background material

- https://react.dev/learn/importing-and-exporting-components
- https://react.dev/learn/passing-props-to-a-component


### 2. Create a Dice Roller

#### Goal

- Sending data up to the parent through a prop. 

#### Tasks

Create a `DiceRoller` component with a button, it should generate a random number between 1 and 6, and send it to its parent.

- [ ] A separate `DiceRoller` component should be created.
- [ ] A button must be rendered by the `DiceRoller` component.
- [ ] A prop should be existed on the component to handle the `onRoll` "event".
- [ ] If a button is clicked, the prop should be called, and passed a random number between 1-6 to the function.
- [ ] The component must be included in the `App`.
- [ ] The `App` must pass down a function to a `onRoll` event. 
- [ ] The `App` must log to the console the given number.

#### Background material

- https://react.dev/learn/responding-to-events

### 3. Connect the Dice with the Dice Roller

#### Goal
  - Updating a state of the component.

#### Tasks

If the DiceRoller's button is clicked, the the Dice component must display the generated number.

- [ ] A `roll` state should be created in the `App` component.
- [ ] If the button is clicked in the DiceRoller, a state should be set in the `App`.
- [ ] If the state is changed, it should update the `Dice` component.

#### Background material

- https://react.dev/learn/state-a-components-memory
- (extra) https://react.dev/learn/render-and-commit
- (extra) https://react.dev/learn/state-as-a-snapshot


### 4. Collect the previous rolls

#### Goal

  - Updating a state when the data is an array.
  - Display a list in react.
  - Do a conditional rendering.

#### Tasks 

Collect the rolls, display them in a new component as an `<ul>`, `<li>` html list.

- [ ] A new `rolls` state should be created in App.js, to store the previous rolls.
- [ ] If a new roll is occured, it should be added to the `rolls` state.
- [ ] A new `DiceHistory` component should be created to display an array of numbers as a list like:

```html
  <ul>
    <li>4</li>
    <li>2</li>
  </ul>
```
- [ ] A new component must receive the rolls as a prop.
- [ ] If the list is empty, it should display the "No dice rolls yet." text.
- [ ] A new component must be included in the App component.

#### Background material

- https://react.dev/learn/updating-arrays-in-state
- https://react.dev/learn/conditional-rendering
- https://react.dev/learn/rendering-lists

### 5. Extend the roll model

#### Goal
  - Introduce an array of objects as a state

#### Tasks

Change the array of numbers to array of objects. Each object represents one roll. The roll has the following properties:

- `roll`: the number what is rolled.
- `isSelected`: a boolean, by default it is false.
- `id`: a unique ID, use the `nextId()` function to generate it.  

- [ ] The rolls should be collected as an objects.
- [ ] The `Dice` component should display the properly the current roll.
- [ ] The `DiceHistory` component should display the previous rolls properly.
- [ ] The react warning about a key prop must be disappear from the console.

#### Background material

- https://react.dev/learn/rendering-lists#keeping-list-items-in-order-with-key
- https://react.dev/learn/updating-arrays-in-state#adding-to-an-array


### 6. Selecting a roll in a history

#### Goal

  - Selecting an item from a list.

#### Task

Make a roll selectable from a `DiceHistory` by adding a select button next to each roll.

- [ ] A button with "Select" text is displayed next to each number in the dice history.
- [ ] An `onSelect` prop is defined in the `DiceHistory` component.
- [ ] The roll's ID must be sent to the `App`, if a user clicks on the button. The `App` should log it to the console.

### 7. Modifying the roll's state

#### Goal
  
- Updating a state of an array of objects.

#### Tasks

When a roll is selected, it should be displayed as bold with the `<strong></strong>` element.

- [ ] When an `onSelect` is happened in the `DiceHistory`, an app should update the particular roll in the `rolls` state. (toggle the `isSelected` prop of the roll).
- [ ] The `DiceHistory` component must display the selected elements as strong.
- [ ] If the user clicks on the select button next to a selected element, it should change back to normal element (in the `rolls` state and also visually).

#### Background material

- https://react.dev/learn/updating-arrays-in-state#replacing-items-in-an-array

### 8. Remove a roll

#### Task

Create button next to each roll in a `DiceHistory` element. If the users click on it, remove that paricular roll from the list. 

#### Background meterial
- https://react.dev/learn/updating-arrays-in-state#removing-from-an-array)

### 9. Yahtzee

Implement a simplified [yahtzee](https://en.wikipedia.org/wiki/Yahtzee) game from this state. Freestyle task.

You can reuse the components from the previous exercises.

Goal: 

- Play a little bit around what you have learned.

Features, obligatory:

- At most 6 rolls you have. If 6 rolls are displayed, the Roll button should be disabled. If you remove a dice, you can add a roll again. You can not remove a selected dice.

- If a dice [category](https://en.wikipedia.org/wiki/Yahtzee#Lower_section) is selected, show its name in a separate component. (3 of a kind, 4 of a kind, yahtzee, full house support is enough). In a case of multiple categories are matching, the category with the highest score should be displayed.

- Support for restart of the game.


Extra features ideas:

- Support for automatic remove and reroll of all non selected rolls.
- Introduce turns. The user can re-roll at most 3 times in a turn. The final category's score is displayed to the user after 3 turns.
- Introduce turn history. Record each turn's score, show the last 10 turn's score to the user.
- Display a summary of the last 10 turn's score. 
- Show the scores next to detected category.
- Support for all roll categories.
- Display dice faces instead of numbers.
- ... etc
