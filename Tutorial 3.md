---
tags:
  - code
  - U19
  - CSharp
date: 2023-09-02 14:26
File Modified: 2023-09-17 15:38
File Folder: ProjectBinTendoDs
Type: Tutorial
---

---

**Tutorial: Creating a Windows Forms Application for Number Conversion - Part 3**

**Introduction**:
Welcome to Part 3 of the Number Converter App tutorial series. In this part, we will begin implementing the core logic for numeric conversions. We'll handle conversions from Denary (Decimal) to other formats like Binary, Hexadecimal, ASCII, and Octal.

**Prerequisites**:
- Completion of Parts 1 and 2 of this tutorial series.
- Visual Studio or another C# IDE.

**Part 3: Implementing Numeric Conversions (30 minutes)**

*Step 1: Create Helper Methods for Numeric Conversions*
1. In your Form Designer, open the code-behind file for your form.
2. Create helper methods for each type of conversion you want to handle, e.g., `ConvertToBinary`, `ConvertToHexadecimal`, `ConvertToASCII`, and `ConvertToOctal`.
3. These methods should accept a Denary (Decimal) input and return the converted value.

*Step 2: Implement the Conversion Logic*
4. In the event handler for the "Convert" button, get the user's input from the text box.
5. Convert this input to an integer using `int.TryParse`.
6. Depending on which radio button is selected, call the appropriate conversion method.
7. Update the output text box with the result.

```csharp
// Example for Binary conversion
private string ConvertToBinary(int denaryValue)
{
    return Convert.ToString(denaryValue, 2);
}

private void buttonConvert_Click(object sender, EventArgs e)
{
    // Read the user input from the input TextBox
    string userInput = textBoxInput.Text;

    // Check which conversion type is selected
    if (radioButtonBinary.Checked)
    {
        if (int.TryParse(userInput, out int denaryValue))
        {
            // Call the Binary conversion method
            string binaryValue = ConvertToBinary(denaryValue);
            textBoxOutput.Text = binaryValue;
        }
        else
        {
            MessageBox.Show("Invalid denary input. Please enter a valid number.");
        }
    }
    // Similar logic for other conversions
}
```

*Step 3: Test Numeric Conversions*
8. Save your changes and run your application.
9. Enter a Denary (Decimal) number, select a conversion type, and click the "Convert" button.
10. The output text box should display the converted value.

*Step 4: Recap*
In Part 3, you've learned how to:
- Create helper methods for numeric conversions.
- Implement conversion logic based on user input and radio button selection.
- Test the conversion functionality for Binary, and you can repeat this process for other conversions.

In Part 4, we'll enhance error handling and add more conversion options to our Number Converter App. Stay tuned for more features!
