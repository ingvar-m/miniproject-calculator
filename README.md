# 🧮 Retro Calculator

An interactive, retro-style calculator application built with Flutter. It parses complex mathematical expressions using a custom two-stack algorithm and the Interpreter design pattern to build an executable math tree.

## Technologies

* **Flutter**
* **Dart**
* **ChangeNotifier / ListenableBuilder** (State Management)

## Features

* **Custom Expression Parser:** Converts flat string inputs into structured mathematical tokens.
* **Smart Input Validation:** Catches errors before parsing (e.g., prevents double decimals, distinguishes standard minus from unary).
* **Mathematical Priority:** Uses two stacks to ensure multiplication/percentages are executed before addition.
* **Scalable Architecture:** Built with the Interpreter pattern. Each operation is a self-contained object, allowing a tree of any depth without changing the core code.
* **Retro UI/UX:** Features a multi-colored layering system for a pixel-style 3D look, with `AnimatedPositioned` imitating physical key presses.

## The Process

I started by breaking down the input string into a clean list of tokens. To maintain mathematical order, I implemented a parser using two stacks: one for values and one for operators. 

This allowed me to build a mathematical tree where numbers become leaves, and operators become the nodes connecting them. To avoid a giant `switch` statement for calculations, I applied the interpreter pattern. Every operation inherits from a base `Expression` class and implements its own `interpret` method. 

The UI triggers the `CalculatorController`, which validates the input. On pressing "equal", the `CalculatorParser` builds the tree and calculates the result from the bottom up.

## Running the Project

1. Create a new Flutter project.
2. Navigate into your new project directory.
3. Replace the contents of the newly created lib folder with the files from this repository.
4. Open the pubspec.yaml file and add the required dependencies:
```yaml
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8
  google_fonts: ^6.1.0
```
5. Install the dependencies.
6. Connect an Android device or start an Android emulator, then run.

## Preview

![App Demo](https://github.com/ingvar-m/miniproject-calculator/blob/main/simple_calculator.gif)
