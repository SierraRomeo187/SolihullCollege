---
tags:
  - code
  - U19
  - CSharp
date: 2023-09-02 14:26
File Modified: 2023-09-17 15:36
File Folder: ProjectBinTendoDs
Type: Tutorial
---

---
**Tutorial: Creating a Windows Forms Application for Number Conversion - Part 2**

**Introduction**:
Welcome to Part 2 of the Number Converter App tutorial series. In this part, we'll dive into event-driven programming and learn how to make the UI elements functional. You'll also create event handlers for the radio buttons and conversion button.

**Prerequisites**:
- Visual Studio or another C# IDE.
- Completion of Part 1 of this tutorial series.

**Part 2: Implementing Event Handlers (15 minutes)**

*Step 1: Understanding Event-Driven Programming*
1. In Windows Forms, UI elements raise events when actions occur (e.g., button click or radio button selection).
2. You write event handlers to respond to these events and perform actions.

*Step 2: Create Event Handlers for Radio Buttons*
3. In the Form Designer, double-click on the Binary radio button (`radioButtonBinary`).
4. Visual Studio will generate an event handler method for the `CheckedChanged` event of this radio button.
5. Inside the event handler, write code to handle the event. For example, you can display a message: `MessageBox.Show("Binary radio button checked!");`
6. Repeat the same process for other radio buttons (Hexadecimal, ASCII, Octal).

*Step 3: Create an Event Handler for the Conversion Button*
7. Double-click on the "Convert" button (`buttonConvert`).
8. Visual Studio will generate an event handler method for the Click event of this button.
9. Inside the event handler, we'll add code to perform conversions. We'll implement this functionality in subsequent parts.

*Step 4: Test the Event Handlers*
10. Save your changes and run your application.
11. Check if the event handlers are working by clicking the radio buttons. You should see the message boxes when each radio button is selected.
12. Test the conversion button as well; it should respond to clicks.

*Step 5: Recap*
In Part 2, you've learned how to:
- Create event handlers for radio buttons and the conversion button.
- Respond to events raised by UI elements.

In Part 3, we'll start implementing the logic for numeric conversions. Stay tuned to build the core functionality of your Number Converter App!

