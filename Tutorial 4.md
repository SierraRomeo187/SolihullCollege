---
tags:
  - code
  - U19
  - CSharp
date: 2023-09-02 14:26
File Modified: 2023-09-17 15:40
File Folder: ProjectBinTendoDs
Type: Tutorial
---

---

**Tutorial: Creating a Windows Forms Application for Number Conversion - Part 4**

**Introduction**:
Welcome to Part 4 of the Number Converter App tutorial series. In this part, we will enhance our application by adding more conversion options, handling errors more gracefully, and implementing an output format selection dropdown.

**Prerequisites**:
- Completion of Parts 1, 2, and 3 of this tutorial series.
- Visual Studio or another C# IDE.

**Part 4: Expanding Functionality (45 minutes)**

*Step 1: Add Conversion Methods*
1. Create additional helper methods for converting to Hexadecimal, ASCII, and Octal formats following the same pattern as Part 3's `ConvertToBinary` method.

```csharp
// Example for Hexadecimal conversion
private string ConvertToHexadecimal(int denaryValue)
{
    return denaryValue.ToString("X");
}
```

*Step 2: Implement Error Handling*
2. Improve error handling by showing more specific error messages for each conversion type.

```csharp
if (!int.TryParse(userInput, out int denaryValue))
{
    MessageBox.Show("Invalid denary input. Please enter a valid number.");
    return;
}
```

*Step 3: Add ComboBox for Output Format*
3. In your Form Designer, drag and drop a ComboBox control named `comboBoxOutputFormat` onto your form.
4. Populate the ComboBox with the available output formats, such as "Denary," "Binary," "Hexadecimal," "ASCII," and "Octal."
5. In the `comboBoxOutputFormat_SelectedIndexChanged` event handler, get the selected output format and update the output text accordingly.

```csharp
private void comboBoxOutputFormat_SelectedIndexChanged(object sender, EventArgs e)
{
    if (int.TryParse(textBoxInput.Text, out int denaryValue))
    {
        string selectedFormat = comboBoxOutputFormat.SelectedItem.ToString();
        
        // Perform the conversion based on the selected format
        string convertedValue = string.Empty;
        switch (selectedFormat)
        {
            case "Denary":
                convertedValue = denaryValue.ToString();
                break;
            case "Binary":
                convertedValue = ConvertToBinary(denaryValue);
                break;
            case "Hexadecimal":
                convertedValue = ConvertToHexadecimal(denaryValue);
                break;
            case "ASCII":
                convertedValue = ConvertToASCII(denaryValue);
                break;
            case "Octal":
                convertedValue = ConvertToOctal(denaryValue);
                break;
        }

        textBoxOutput.Text = convertedValue;
    }
    else
    {
        MessageBox.Show("Invalid denary input. Please enter a valid number.");
    }
}
```

*Step 4: Test the Updated Application*
6. Save your changes and run your application.
7. Enter a Denary (Decimal) number, select an output format from the dropdown, and click the "Convert" button.
8. The output text box should display the converted value in the selected format.

*Step 5: Recap*
In Part 4, you've learned how to:
- Create helper methods for additional numeric conversions (Hexadecimal, ASCII, and Octal).
- Improve error handling by providing specific error messages.
- Add a ComboBox for selecting the desired output format.
- Dynamically update the output based on the selected format.

In Part 5, we'll finalize our Number Converter App by improving the user interface, adding comments for code clarity, and preparing it for distribution. Stay tuned for the final touches!
