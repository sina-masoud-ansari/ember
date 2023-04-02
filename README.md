# Ember

## What is it?

A framework for specifying interactive games to large language models (LLMs) such as ChatGPT/GPT-4

## How does it work?

The framework is currently being deveolped for ChatGPT/GPT-4 and requires specifying a few files and pasting them into ChatGPT. The files are:

* **setup.txt**
  * This plain text file is the first file that should be given to ChatGPT and lets it know what to expect. It can be found and `prompts` and customised to your needs.
* **world.json**
  * This JSON file defines the background, characters, locations and details of the world your story takes place in.
* **log.json**
  * This JSON file is use to save the state of your game, recording key events and the player character definition along with the status and inventory if required
* **game.json**
  * This JSON file define how your game works

The `world`, and `game` JSON files are unique to each game world and the `log` is unique to each instance of a game. The idea is that you can periodically save your game state and resume it as needed e.g. if the LLM context window is exceeded or you want to try it with a different model.

## Worlds

An example (work in progress) world can be found in `worlds/the-island`. This is simple example but the ideas is to include public domain works in the future so you can play a game in the world of Sherlock Holmes for instance.

## Example

Here is an example of the output from an initial version of this approach using ChatGPT with GPT-4, note these characters have been created by ChatGPT as part of an earlier process and the output has been formatted for readability:

```
> paste prompts/setup.txt
```
```
Please provide the contents of world.json, game.json, and log.json files.
I will confirm each input with "input confirmed".
Once all input files have been provided, please enter "GM start" to begin the game.
```
```
world.json:

> paste worlds/the-island/world.json
```
```
input confirmed
```
```
game.json:

> paste worlds/the-island/game.json
```
```
input confirmed
```
```
log.json:

> paste worlds/the-island/log.json
```
```
input confirmed

Please enter "GM start" to begin the game.
```
```
GM start
```
```
Welcome to this survival thriller and action-adventure game. Your objective is to survive and find a way to get off the island.

First, let's create your character. Please provide the following attributes:

Name
Age
Sex
Background
Next, select 2 items from the following list of starting items:

Lighter
Deck of playing cards
500ml water bottle
Knife with a 7cm blade
First aid kit
Finally, provide your character's strength (low, medium, high) and fitness (low, medium, high).
```
```
Name: Olivia Thompson
Age: 32
Sex: Female
Background: A high school economics teacher
Starting items: 500ml water bottle, Deck of playing cards
Strength: medium
Fitness: medium
```
```
Character created:

Name: Olivia Thompson
Age: 32
Sex: Female
Background: A high school economics teacher
Starting items: 500ml water bottle, Deck of playing cards
Strength: medium
Fitness: medium
Health: healthy

Updating log.json:

{
"character": {
"name": "Olivia Thompson",
"age": 32,
"sex": "Female",
"background": "A high school economics teacher",
"starting_items": [
"500ml water bottle",
"Deck of playing cards"
],
"strength": "medium",
"fitness": "medium",
"health": "healthy"
},
"log": []
}

Olivia, you slowly regain consciousness, feeling the cool, damp sand beneath you. 
You open your eyes to see a beautiful but unfamiliar beach.
The sound of crashing waves fills your ears,
and the remnants of the stormy sky are gradually clearing.
You realize that you have washed up on an island.

Around you, there's debris scattered across the beach from the plane crash.
A short distance away, you see Isabella Martinez, a former soldier and ship captain,
and Dr. Marcus Caldwell, a scientist and botanist,
who are also waking up and looking just as disoriented as you.

What would you like to do?
```
```
I check myself for injuries, take stock of what I have on me and I approach Isabella to say hello
```
```
You quickly check yourself for any injuries and find that you're mostly unharmed,
apart from a few scrapes and bruises.
You have your 500ml water bottle and a deck of playing cards with you.

You approach Isabella, who seems to be gathering herself after the crash.
She notices you coming closer and gives you a cautious but friendly smile.

"Hey, I'm Isabella. Looks like we're in quite a situation, huh?" she says,
trying to lighten the mood despite the circumstances. "Are you okay?"

What would you like to say or do next?
```
```
I think I'm ok, where are we?
```
```
Isabella looks around and then back at you, shaking her head.
"I'm not exactly sure. We must have drifted for hours before washing up on this island.
I haven't seen any signs of civilization or other survivors yet,
but maybe there's something further inland."

Dr. Marcus Caldwell, who has been quietly listening to your conversation, interjects,
"I overheard you talking. We should probably stick together and explore the island,
at least until we figure out where we are and if there's a way to signal for help."

What would you like to do or say next?
```